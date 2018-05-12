Flogo apps are constructed using a JSON file called `flogo.json`. You can create those files using the Flogo Web UI, or you can create them manually. 

#### flogo.json
Now let's create the flogo.json file. To do that, execute `touch flogo.json`{{execute}} in the terminal, which will create a new empty file for you.

Now you can copy the contents below to the newly created flogo.json file (you can use the **copy to clipboard** option at the bottom of the text field). The Flogo app has a Lambda trigger which can be triggered by any event supported by AWS Lambda. You can click on the code, which will copy it to your clipboard. Now click on `flogo.json` in the editor window and paste.
```
{
  "name": "Tutorial",
  "type": "flogo:app",
  "version": "0.0.1",
  "appModel": "1.0.0",
  "triggers": [
    {
      "id": "start_flow_as_a_function_in_lambda",
      "ref": "github.com/TIBCOSoftware/flogo-contrib/trigger/lambda",
      "name": "Start Flow as a function in Lambda",
      "description": "Simple Lambda Trigger",
      "settings": {},
      "handlers": [
        {
          "action": {
            "ref": "github.com/TIBCOSoftware/flogo-contrib/action/flow",
            "data": {
              "flowURI": "res://flow:lambda_flow"
            },
            "mappings": {
              "input": [
                {
                  "mapTo": "name",
                  "type": "assign",
                  "value": "$.evt.name"
                }
              ],
              "output": [
                {
                  "mapTo": "data",
                  "type": "assign",
                  "value": "$.greeting"
                }
              ]
            }
          }
        }
      ]
    }
  ],
  "resources": [
    {
      "id": "flow:lambda_flow",
      "data": {
        "name": "LambdaFlow",
        "metadata": {
          "input": [
            {
              "name": "name",
              "type": "string"
            }
          ],
          "output": [
            {
              "name": "greeting",
              "type": "any"
            }
          ]
        },
        "tasks": [
          {
            "id": "log_2",
            "name": "Log Message",
            "description": "Simple Log Activity",
            "activity": {
              "ref": "github.com/TIBCOSoftware/flogo-contrib/activity/log",
              "input": {
                "message": "",
                "flowInfo": "false",
                "addToFlow": "false"
              },
              "mappings": {
                "input": [
                  {
                    "type": "expression",
                    "value": "string.concat(\"Hello \", $flow.name)",
                    "mapTo": "message"
                  }
                ]
              }
            }
          },
          {
            "id": "actreturn_3",
            "name": "Return",
            "description": "Simple Return Activity",
            "activity": {
              "ref": "github.com/TIBCOSoftware/flogo-contrib/activity/actreturn",
              "input": {
                "mappings": [
                  {
                    "mapTo": "greeting",
                    "type": "object",
                    "value": {"Hello": "{{$flow.name}}"}
                  }
                ]
              }
            }
          }
        ],
        "links": [
          {
            "from": "log_2",
            "to": "actreturn_3"
          }
        ]
      }
    }
  ]
}
```{{copy}}