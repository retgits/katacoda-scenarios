Activities are the units of work, and those carry out the actual tasks in the flow. Think of them as methods in other programming languages.

#### Add a log activity
You can add activities to the canvas by clicking the `+` button. Let's add a new **Log Message** activity to the service by clicking on the icon and choosing the **Log Message**. By default you'll have a bunch of activities to choose from and just as with triggers, if none of them fit your needs, you can either create new ones yourself or look at the [community](https://tibcosoftware.github.io/flogo/showcases/). The Log activity will give the flow the ability to write data to the standard output. As you hover over it, a panel will slide out and you can select **configure** to start configuring your activity.

The configuration should be as follows:

* message: `string.concat("Hello ", $flow.name)` (this will take the name you passed into the flow as a parameter and log a hello)

_Note: you can leave `flowInfo`and `addToFlow` blank_
