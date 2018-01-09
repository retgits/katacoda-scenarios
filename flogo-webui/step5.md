We're definitely making progress here! Now we know the flow will be started with an HTTP trigger, and we can configure it. 

#### Configure the trigger
When you click on the trigger you just created, a slide out panel will appear with an option for `Configure`. Click on that option to open the configuration pane on the right hand side of the screen. There are five settings that we'll configure:

* **port**: The HTTP port on which this flow should listen. For this example we’ll use 8080
* **method**: The HTTP method that will trigger the flow. To make testing a bit easier we’ll use the get method so we can test it from the browser
* **path**: The path for the flow to listen to. We’ll set this to `/helloworld`
* **autoIdReply**: Should the flow automatically reply with the identifier the flow. You can set that to `true`
* **useReplyHandler**: Should the flow send data back. In this case we’ll choose `true` to make sure we see something in the browser as the end result

#### Tip
The URL on which our microservice will listen will be `http://localhost:8080/helloworld`. If you made changes to any of the variables above, please make sure to change those in the rest of these examples.