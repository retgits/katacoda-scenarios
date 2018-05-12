We've just started you off with a brand new environment that just has Go installed. The grey blocks you'll see through this tutorial mean they are terminal commands which will be executed when you click on them. Alternatively, you can also type them in the terminal yourself. 

#### Get the CLI
You'll need to go get the Flogo cli to work with Project Flogo. To do so simply run `go get -u github.com/TIBCOSoftware/flogo-cli/...`{{execute}}

#### Go dep
In order to simplify dependency management, we’re using the go dep tool. The easiest way to get this in your environment is to download the latest binary for your machine. You can do that on this environment by running `curl -Lo /gopath/bin/dep https://github.com/golang/dep/releases/download/v0.4.1/dep-linux-amd64 && chmod +x /gopath/bin/dep`{{execute}}