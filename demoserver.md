# OMGSERVERS Demo Server Instructions

You have received developer account credentials for the demo server.

You can interact with the demo server in different roles:

- **Developer**
- **Player**

## How to Use a Developer Account

### Step 1: Configure a VPN Connection

- You need to set up a VPN connection using a WireGuard VPN client:
    - Download the WireGuard client for your platform from here: [WireGuard Install](https://www.wireguard.com/install/)
    - Install the client and establish a connection using your personal VPN configuration.
    - Once the VPN connection is established, the internal `demoserver.omgs.cc` address will become accessible.

### Step 2: Access `demoserver.omgs.cc`

- **Developer API Access:**  
  Utilize the **OMGSERVERS CTL** tool to interact with the developer
  API. [See detailed instructions here](https://github.com/OMGSERVERS/omginstructions/blob/main/omgserversctl.md).

- **Docker Image Management:**  
  To log in to the demoserver registry to push your game runtime Docker images:
  ```bash
  docker login -u ${DEVELOPER_USER} -p ${DEVELOPER_PASSWORD} "demoserver.omgs.cc"
    ```

- **Monitoring and Logs:**  
  Access monitoring and log retrieval
  at [`https://demoserver.omgs.cc/monitoring`](https://demoserver.omgs.cc/monitoring).

### Step 3: Building Your Game Server Runtime

- Create your game project and integrate the [OMGSERVERS SDK](https://github.com/OMGSERVERS/omgdefold) into it.
- Build a Docker image with your game runtime.
- Tag and push your Docker image to the demo server registry using the appropriate image name and tag:
  ```bash
  docker tag "game:latest" "demoserver.omgs.cc/omgservers/${TENANT}/${PROJECT}/universal:${VERSION}"
  docker push "demoserver.omgs.cc/omgservers/${TENANT}/${PROJECT}/universal:${VERSION}"
  ```

## How to Interact as a Player to Test Your Game

### Step 1: Know Your Project Connection Parameters

To connect your game, you need the following parameters:

- **Server URL:** `https://demoserver.omgservers.com`
- **Tenant:** `<tenant>`
- **Project:** `<project>`
- **Stage:** `<stage>`

### Step 2: Integrate the OMGPLAYER SDK

- Integrate the [OMGPLAYER SDK](https://github.com/OMGSERVERS/omgdefold) into your game client.
- Configure it using the connection parameters listed above.

Once configured, you can run and test your multiplayer game on OMGSERVERS.






