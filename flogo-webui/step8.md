The reply handler is used to make sure you can send information back when your service is invoked

#### Add a reply handler
The last step in the flow is to add a reply handler. You can do that in the same way we just added the Log activity in the previous step. Click on the `+` button and choose the **Reply To Trigger** activity.

#### Configure it
Click on the new activity and you'll be prompted with a new dialog windows to map flow outputs. Click on **message** on the left hand side of the screen (which is the flow param you created earlier). Now click on the little triangle next to **log_2 (Log Message)** to expand the tree and click on **message** to map the output of the Log Message activity to the flow param called message.

#### One final mapping step
The last step to complete the mappings is to map all the output to the trigger reply. When you click on the trigger you created, a slide out panel will appear with an option for `Map flow params`. Click on that option to open the configuration pane. Select the option for **Trigger Reply** on the left hand side and click on `1.. code`. Type the value `200` in the input box, which means you'll hardcode the value for code. While usually not a best practice to hardcode things, it is an easy way to test. Now click on `{} data` and instead of typing a value, click on `a.. message` underneath the box. This means you'll map the flow parameter **message** as part of the output.