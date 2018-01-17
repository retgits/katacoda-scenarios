In this step we'll construct the source code for the Flogo app from the flogo.json as well as create the app!

To create the source code simply execute `flogo create -f flogo.json myapp`{{execute}}. This tells the flogo cli to take the flogo.json file and create the source for the app in a folder called `myapp`. It will also download a few Go packages that the app will need.

The next step is to build the executable and for that we need to be in the directory `myapp` (`cd myapp`{{execute}}). To build a flogo app from the source you can execute the command `flogo build -e`{{execute}}, which tells the flogo cli to build the app (and place it in a bin directory) and embed all configuration into a single executable