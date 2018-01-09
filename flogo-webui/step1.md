Installing the Flogo Web UI is quite simple and requires nothing more than having Docker installed on your machine. As you can see in the terminal on the right side of the screen, we've already began launching the container for you, to give you a flying start!

To launch the container we used the below command:

```
docker run -it -p 3303:3303 flogo/flogo-docker:latest eula-accept
```

It will take a few seconds to download the image and start the container for you, so please bare with us until you see

```
[success] open http://localhost:3303 in your browser
```

Everything is now fully configured and awaiting your first steps in the world of Project Flogo.

#### Load Dashboard

To launch Flogo WebUI simply open your favorite web browser, and navigate to https://[[HOST_SUBDOMAIN]]-3303-[[KATACODA_HOST]].environments.katacoda.com/ or using the `Web UI` tab from the console. You’ll see our mascot Flynn there to greet you!

In the next steps, you'll use the Web UI to create your new microservice.