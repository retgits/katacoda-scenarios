The reply handler is used to make sure you can send information back when your service is invoked

#### Add a reply handler
The last step in the flow is to add a reply handler. You can do that in the same way we just added the Log activity in the previous step. Click on the `+` button and choose the **Return** activity.

#### Configure it
Hover over the new activity select **configure** to start mapping. Click on **greeting** on the left hand side of the screen (which is the flow param you created earlier). You can paste in `string.concat("Hello ", $flow.name)` and click the big blue **save** button to complete this step. This will return the same hello statement we logged in the earlier step.

#### One final mapping step
The last step to complete the mappings is to map all the input and output to the trigger. Hover over the trigger you created, a slide out panel will appear with an option for `Configure`. Click on that option to open the configuration pane. 

You'll start off in the `Map to flow inputs` screen. On this screen click on `a.. name`. Type `$.pathParams.name` in the input box, which means you'll map the name parameter from the URL to this field.

Next, select the option for **Map from flow output** on the top of the screen. From here, click on `1.. code`. Type the value `200` in the input box, which means you'll hardcode the value for code. While usually not a best practice to hardcode things, it is an easy way to test. Now click on `* data` and instead of typing a value, click on `a.. greeting` underneath the box. This means you'll map the flow parameter **greeting** as part of the output. Click the big blue **save** button to complete this step.