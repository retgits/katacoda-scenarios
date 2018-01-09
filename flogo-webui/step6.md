You can add activities to the canvase by clicking the `+` button. Let's add a new **Log activity** to the service by clicking on the icon and choosing the **Log activity**. By default you'll have a bunch of activities to choose from and just as with triggers, if none of them fit your needs, you can either create new ones yourself or look at the [community](https://tibcosoftware.github.io/flogo/showcases/). The Log activity will give the flow the ability to write data to the standard output. The message parameter is what you want to write to the log, so for now we’ll simply add Hello World

The configuration should be as follows:

* message: `Hello World`
* flowInfo: `True`
* addToFlow: `False`