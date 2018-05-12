Flogo apps are constructed using a JSON file called `flogo.json`. You can create those files using the Flogo Web UI, or you can create them manually. 

#### flogo.json
Now let's create the flogo.json file. To do that, execute `touch flogo.json`{{execute}} in the terminal, which will create a new empty file for you.

Now you can copy the contents below to the newly created flogo.json file (you can use the **copy to clipboard** option at the bottom of the text field). The Flogo app has a REST trigger which listens on port 9233 and the HTTP path `/test/:name` (where :name is a parameter you can fill in). You can click on the code, which will copy it to your clipboard. Now click on `src -> tutorial -> flogo.json` in the editor window and paste.
```
{
  "name": "Tutorial",
  "type": "flogo:app",
  "version": "0.0.1",
  "appModel": "1.0.0",
  "triggers": [
    {
      "id": "receive_http_message",
      "ref": "github.com/TIBCOSoftware/flogo-contrib/trigger/rest",
      "name": "Receive HTTP Message",
      "description": "Simple REST Trigger",
      "settings": {
        "port": "9233"
      },
      "handlers": [
        {
          "action": {
            "ref": "github.com/TIBCOSoftware/flogo-contrib/action/flow",
            "data": {
              "flowURI": "res://flow:http_flow"
            },
            "mappings": {
              "input": [
                {
                  "mapTo": "name",
                  "type": "assign",
                  "value": "$.pathParams.name"
                }
              ],
              "output": [
                {
                  "mapTo": "data",
                  "type": "assign",
                  "value": "$.greeting"
                },
                {
                  "mapTo": "code",
                  "type": "literal",
                  "value": 200
                }
              ]
            }
          },
          "settings": {
            "method": "GET",
            "path": "/test/:name"
          }
        }
      ]
    }
  ],
  "resources": [
    {
      "id": "flow:http_flow",
      "data": {
        "name": "HTTPFlow",
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
              "type": "string"
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
                    "type": "expression",
                    "value": "string.concat(\"Hello \", $flow.name)",
                    "mapTo": "greeting"
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