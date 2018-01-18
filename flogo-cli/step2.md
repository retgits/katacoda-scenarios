Flogo apps are constructed using a JSON file called `flogo.json`. You can create those files using the Flogo Web UI, or you can create them manually. 

The first step is to create the file. To do that, execute `touch flogo.json`{{execute}} in the terminal, which will create a new empty file for you.

Now you can copy the contents below to the newly created flogo.json file. The Flogo app has a REST trigger which listens on port 9233. You can click on the code, which will copy it to your clipboard. Now click on `flogo.json` in the editor window and paste.
```
{
  "name": "myApp",
  "type": "flogo:app",
  "version": "0.0.1",
  "description": "My flogo application description",
  "triggers": [
    {
      "id": "my_rest_trigger",
      "ref": "github.com/TIBCOSoftware/flogo-contrib/trigger/rest",
      "settings": {
        "port": "9233"
      },
      "handlers": [
        {
          "actionId": "my_simple_flow",
          "settings": {
            "method": "GET",
            "path": "/test"
          }
        }
      ]
    }
  ],
  "actions": [
    {
      "id": "my_simple_flow",
      "ref": "github.com/TIBCOSoftware/flogo-contrib/action/flow",
      "data": {
        "flow": {
          "attributes": [],
          "rootTask": {
            "id": 1,
            "type": 1,
            "tasks": [
              {
                "id": 2,
                "type": 1,
                "activityRef": "github.com/TIBCOSoftware/flogo-contrib/activity/log",
                "name": "log",
                "attributes": [
                  {
                    "name": "message",
                    "value": "Simple Log",
                    "type": "string"
                  }
                ]
              }
            ],
            "links": [
            ]
          }
        }
      }
    }
  ]
}
```{{copy}}