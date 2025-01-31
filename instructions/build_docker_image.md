# How to Build a Docker Image

The project template includes a [Dockerfile](https://github.com/OMGSERVERS/omgdefold/blob/main/Dockerfile) for building
a Docker image that can later be deployed and run by OMGSERVERS.

To start the build process, run the following command:

```sh
./omglocaltestingctl.sh build
```

This command builds an image with the name specified in
the [omglocaltestingctl.env](https://github.com/OMGSERVERS/omgdefold/blob/main/omglocaltestingctl.env) file via the
`DOCKER_IMAGE` variable.