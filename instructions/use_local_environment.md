# How to Use Local Environment

The script `./omglocaltestingctl.sh` allows you to:

- Start and stop the local environment
- Initialize a tenant and developer account
- Build and deploy a new Docker image to test it

Run `./omglocaltestingctl.sh help` to see all available options.

## How It Works

It runs containers in Docker using the `compose.yaml` file from the `localtesting` folder.  
The following containers are started:

- gateway – exposes port 8080 on localhost and routes requests between containers.
- registry – stores Docker images.
- dispatcher – manages WebSocket clients and runtime connections.
- service – implements OMGSERVERS logic.
- broker – delivers events across multiple service instances (not applicable in the local environment).
- database – stores backend data.
- docker – provides access to the Docker daemon via HTTP instead of a Unix socket, which requires root user permissions.