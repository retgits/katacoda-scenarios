We have just built the Flogo app, so now we can test it. From the bin directory (`cd bin`{{execute}}) you can run `./myapp`{{execute}} which will start the app. In the terminal you'll see something like

<pre>
2018-05-12 04:34:56.434 INFO   [engine] - Engine Starting...
2018-05-12 04:34:56.435 INFO   [engine] - Starting Services...
2018-05-12 04:34:56.435 INFO   [engine] - Started Services
2018-05-12 04:34:56.435 INFO   [engine] - Starting Triggers...
2018-05-12 04:34:56.435 INFO   [engine] - Trigger [ receive_http_message ]: Started
2018-05-12 04:34:56.435 INFO   [engine] - Triggers Started
2018-05-12 04:34:56.435 INFO   [engine] - Engine Started
</pre>

To test it we'll use the curl command line tool, which is installed on most Operating Systems. You can start a new terminal window by clicking on the `+` next to Terminal and select `Open New Terminal` from there execute the command `curl http://localhost:9233/test/flogo`{{execute}}. It will send an HTTP request to the app on port 9233 (which was configured in the flogo.json file). In the second terminal you will see the result of the flow (`Hello flogo`) and when you go back to the first terminal you had, you'll see there are additional lines in your window that indicate a flow has been executed

<pre>
2018-05-12 04:35:00.632 INFO   [trigger-flogo-rest] - Received request for id 'receive_http_message'
2018-05-12 04:35:00.632 INFO   [engine] - Running FlowAction for URI: 'res://flow:http_flow'
2018-05-12 04:35:00.633 INFO   [activity-flogo-log] - Hello flogo
2018-05-12 04:35:00.633 INFO   [engine] - Flow instance [29db1cc55a96c27c280227b2d7b8be82] Completed Successfully
2018-05-12 04:35:15.364 INFO   [trigger-flogo-rest] - Received request for id 'receive_http_message'
2018-05-12 04:35:15.364 INFO   [engine] - Running FlowAction for URI: 'res://flow:http_flow'
2018-05-12 04:35:15.364 INFO   [activity-flogo-log] - Hello leon
2018-05-12 04:35:15.365 INFO   [engine] - Flow instance [2adb1cc55a96c27c280227b2d7b8be82] Completed Successfully
</pre>

