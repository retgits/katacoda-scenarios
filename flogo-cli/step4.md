We have just built the Flogo app, so now we can test it. From the bin directory (`cd bin`{{execute}}) you can run `./myapp`{{execute}} which will start the app. In the terminal you'll see something like

<pre>
2018-01-17 14:42:36.060 INFO   [engine] - Engine: Starting...
2018-01-17 14:42:36.061 INFO   [engine] - Engine: Starting Services...
2018-01-17 14:42:36.061 INFO   [engine] - Engine: Started Services
2018-01-17 14:42:36.061 INFO   [engine] - Trigger [my_rest_trigger] started
2018-01-17 14:42:36.061 INFO   [engine] - Engine: Started
</pre>

To test it we'll use the curl command line tool, which is installed on most Operating Systems. You can start a new terminal window by clicking on the `+` next to Terminal and select `Open New Terminal` from there execute the command `curl http://localhost:9233/test`{{execute}}. It will send an HTTP request to the app on port 9233 (which was configured in the flogo.json file). When you go back to the first terminal you had, you'll see there are additional lines in your window that indicate a flow has been executed

<pre>
2018-01-17 14:42:44.362 INFO   [trigger-tibco-rest] - REST Trigger: Received request for id 'my_rest_trigger'
2018-01-17 14:42:44.362 INFO   [engine] - In Flow Run uri: 'my_simple_flow'
2018-01-17 14:42:44.362 INFO   [engine] - FlowInstance Flow: &{tibco-simple 0x16395e8 map[1:0x16395e8]}
2018-01-17 14:42:44.362 INFO   [activity-tibco-log] - Simple Log
2018-01-17 14:42:44.362 INFO   [engine] - Flow [fb77b76729b2b5779bc30654f782d186] Completed
</pre>

