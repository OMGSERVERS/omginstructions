# How to Install a New Version Locally

Once the Docker image is built, you can install it locally to test it using the following command:

```sh
./omglocalctl.sh install
```

## What Happens Under the Hood

This command creates a new project version using `./omgserversctl.sh`:

```sh
./omgserversctl.sh developer createVersion ${TENANT} ${PROJECT} "./config.json"
```

Then, the command logs in to the OMGSERVERS installation registry, tags the built image properly, and pushes it:

```sh
docker login -u ${DEVELOPER_USER} -p ${DEVELOPER_PASSWORD} "localhost:5000"
docker tag ${DOCKER_IMAGE} ${TARGET_IMAGE}
docker push ${TARGET_IMAGE}
```

The correct image name is important; it should follow this
pattern: `<registry_url>/omgservers/${TENANT}/${PROJECT}/universal:${VERSION}`

The final step is to request the version deployment to allow players to connect:

```sh
./omgserversctl.sh developer deployVersion ${TENANT} ${PROJECT} ${STAGE} ${VERSION}
```