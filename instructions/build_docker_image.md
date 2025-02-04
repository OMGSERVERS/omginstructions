# How to Build a Docker Image

The project template includes a [Dockerfile](https://github.com/OMGSERVERS/omgdefold/blob/main/Dockerfile) for building
a Docker image that can later be deployed and run by OMGSERVERS.

To start the build process, run the following command:

```sh
./omglocalctl.sh build
```

This command builds an image with the name specified in
the [omglocalctl.env](https://github.com/OMGSERVERS/omgdefold/blob/main/omglocalctl.env) file via the
`DOCKER_IMAGE` variable.