# Porolog Deployment Package

**Important: It is presumed that all commands are executed from the root directory of this repository!**

## Prerequisites

In order to properly deploy this infrastructure the following packages are required

| Software       | Version                                |
| -------------- | -------------------------------------- |
| docker         | 19.03.5-ce, build 633a0ea838 or higher |
| docker-compose | 2.4.1 or higher                        |

In order to install docker engine follow the [tutorial][docker_tutorial].
In order to install docker-compose follow the [tutorial][docker_compose_tutorial].

## Setup

In order to properly configure the **setup the environmental variables** of .env file must be set approprietly. Also the mosquitto **pwfile file must be overridden** with the appropriate credentials and be placed in the ./mosquitto directory.

To create a mosquitto pwfile simply run:

```sh
mosquitto_passwd -U ./mosquitto/pwfile <user>
```

Note: You will be prompted to enter the user's password twice.

The **MOSQUITTO_USERNAME & MOSQUITTO_USERNAME** must in the .env file be updated accordingly to match the credentials given in the pwfile so as the json-iot-agent is able to connect to the mosquitto broker. Optionally the other environmental variables can also be changed.

## Execution

To create the infrastructure simply execute the following command:

```sh
./launch.sh
```

Note: The script must have execution privilages. Run the following command as superuser if the priviledges are insufficient.

```sh
sudo chmod +x launch.sh
```

[docker_tutorial]: https://docs.docker.com/engine/install/ubuntu/
[docker_compose_tutorial]: < https://docs.docker.com/compose/install/>
