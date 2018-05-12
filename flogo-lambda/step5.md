#### Testing 1... 2... 3...
The only thing left is to test your function. To do that log into AWS and select "Lambda", you'll be presented with all the functions you've deployed so far and one of them will be called `tutorial`. Click on that, and you'll see the overview of your function, including a large button that says "Test". Click "Test" to configure a new test event. The input for the test event should be
```
{
  "name": "World"
}
```
_You can replace "world" with any name or message you want_

From there, click "Test" and the execution logs will display the result

```
{
  "Hello": "World"
}
```

And the log output
```
START RequestId: 4f26990d-561d-11e8-96ca-bb9eb4465310 Version: $LATEST
2018-05-12 19:47:31.969 INFO   [trigger-flogo-lambda] - Starting AWS Lambda Trigger
2018/05/12 19:47:31 Starting AWS Lambda Trigger
2018/05/12 19:47:31 Received evt: 'map[name:World]'
2018/05/12 19:47:31 Received ctx: 'map[logStreamName:2018/05/12/[$LATEST]7f886628e07a4256b0f411b6cd3b6915 memoryLimitInMB:128 awsRequestId:4f26990d-561d-11e8-96ca-bb9eb4465310 functionName:tutorial functionVersion:$LATEST logGroupName:/aws/lambda/tutorial]'
2018-05-12 19:47:31.969 INFO   [activity-flogo-log] - Hello World
$flow.nameEND RequestId: 4f26990d-561d-11e8-96ca-bb9eb4465310
REPORT RequestId: 4f26990d-561d-11e8-96ca-bb9eb4465310	Duration: 1.63 ms	Billed Duration: 100 ms 	Memory Size: 128 MB	Max Memory Used: 23 MB
```

As you're glancing over the results, also look at the _Duration_ and _Max Memory Used_. Isn't that one of the smallest functions you've seen?!