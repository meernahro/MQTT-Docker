
# MQTT Broker Docker Container

This repository provides a Docker Compose setup for running an MQTT broker using Eclipse Mosquitto. The configuration includes a custom `mosquitto.conf` file, which specifies the port for MQTT communication, enables persistence, and sets up data and log directories.

## Prerequisites

Make sure you have Docker and Docker Compose installed on your machine.

- [Docker Installation Guide](https://docs.docker.com/get-docker/)
- [Docker Compose Installation Guide](https://docs.docker.com/compose/install/)

## Getting Started

1. Clone this repository to your local machine:

   ```bash
   git clone https://github.com/meernahro/your-repo.git
   ```

2. Navigate to the repository:

   ```bash
   cd your-repo
   ```

3. Create three folders named `config`, `data`, and `log` in the root of the repository. These folders will be used to store the Mosquitto configuration, data, and log files, respectively.

4. Copy the provided `mosquitto.conf` file into the `config` folder.

5. Your directory structure should look like this:

   ```plaintext
   your-repo/
   |   └── pass.txt
   |   └── docker-compose.yml
   ├── config/
   │   └── mosquitto.conf
   ├── data/
   └── log/
   ```

## Configuring the MQTT Broker

In the `mosquitto.conf` file, two listeners are configured:

- Listener 7891: Requires authentication (username and password) with `allow_anonymous false`.
- Listener 7890: Allows anonymous connections with `allow_anonymous true`.

Update the `pass.txt` file with your desired username and password for secure access. You need to the password file through mosquitto_paswd tool to encrypt the password

## Running the MQTT Broker

Ensure you are in the root directory of the repository (right outside the `mosquitto` folder) before running the following commands.

Run the MQTT broker using Docker Compose:

```bash
docker-compose up
```

This command will build the Docker image and start the containerized Mosquitto MQTT broker. The broker will be accessible on port 7890 for anonymous connections and on port 7891 for authenticated connections.

## Accessing the MQTT Broker

The MQTT broker is now running, and you can connect to it using the specified ports (7890 for anonymous, 7891 for authenticated). Use this broker for your MQTT communication needs.

## Stopping the MQTT Broker

To stop the MQTT broker and remove the container, press `Ctrl + C` in the terminal where the `docker-compose up` command is running. Alternatively, open a new terminal window, navigate to the repository directory, and run:

```bash
docker-compose down
```

This will stop and remove the container, freeing up the used resources.

Feel free to customize the `mosquitto.conf` file and other configurations based on your specific requirements.

Happy MQTT messaging! 🚀
```

