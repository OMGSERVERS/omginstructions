# How to Use OMGSERVERS CTL

The OMGSERVERS CTL tool is shipped as a Docker image. You can pull it using:

```sh
docker pull omgservers/ctl:1.0.0-SNAPSHOT
```

The tool stores credentials, tokens, and various configuration parameters in the `/opt/omgserversctl/.omgserversctl`
directory.

To persist data across executions, you need to mount a volume:

```sh
-v ${PWD}/.omgserversctl:/opt/omgserversctl/.omgserversctl
```

To run the tool on your host, use the following command:

```sh
docker run --rm -it \
    --network=host \
    -v ${PWD}/.omgserversctl:/opt/omgserversctl/.omgserversctl \
    omgservers/ctl:1.0.0-SNAPSHOT
```

A script `omgserversctl.sh` can be created to pass incoming parameters and simplify manual execution:

```sh
#!/bin/bash

docker run --rm -it \
    --network=host \
    -v ${PWD}/.omgserversctl:/opt/omgserversctl/.omgserversctl \
    omgservers/ctl:1.0.0-SNAPSHOT $@
```

Once you are ready to run the tool, let's configure it to use your developer account on the demo server:

```sh
./omgserversctl environment useDemoServer
./omgserversctl developer useCredentials ${DEVELOPER_USER} ${DEVELOPER_PASSWORD}

# Test the configuration
./omgserversctl developer getTenantDetails ${TENANT_ID}
```
