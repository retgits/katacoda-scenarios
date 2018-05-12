We're definitely making progress here! Now we know the flow will be started with an HTTP trigger, and we can configure it. 

#### Configure the trigger
Click on the trigger you just created. There are three settings that we'll configure:

* **port**: The HTTP port on which this flow should listen. For this example we’ll use 9233
* **method**: The HTTP method that will trigger the flow. To make testing a bit easier we’ll use the `GET` method so we can test it from the browser
* **path**: The path for the flow to listen to. We’ll set this to `/test/:name`

#### Tip
The URL on which our microservice will listen will be `http://localhost:9233/test/:name` (the _:name_ is a parameter that you can replace with anything during runtime). If you made changes to any of the variables above, please make sure to change those in the rest of these examples.