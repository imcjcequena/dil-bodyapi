# body-API

Repository for the body API Dockerfile. It assumes that the container is run on a local computer running windows.

## Installation

Running body API from a linux container requires the host to have XServer installed and running. Get it from: https://sourceforge.net/projects/vcxsrv/

## Usage

Running body API from a container requires the container to communicate with the host XServer. This is done while using the docker run command using the following flag:

```
-e DISPLAY=host_XServer_address
```

By default, the Dockerfile is set to assume that the host is running on microsoft windows and XServer is on default settings.

At the same time, the host usb port that is connected to the camera needs to be passed to the container when it is run using the following flag:

```
--device=host_usb_address
```

## Other demos

While the container is set to run body API by default, it can be used to run all the other sample demos included in the SDK by overriding default command run on the container using the optional cmd override:

```
docker run image optional_cmd_override
```

Replace the optional_cmd_override with:

```
./demo_name
```

The available demo_name values are as follows:

1. BodyReaderPoll
2. ColorReaderEvent
3. ColorReaderEventCPP
4. ColorReaderPoll
5. ColorizedBodyViewer-SFML
6. DepthReaderEvent
7. DepthReaderEventCPP
8. DepthReaderPoll
9. InfraredColorReaderEvent
10. InfraredReaderEvent
11. InfraredReaderPoll
12. MaskedColorViewer-SFML
13. MultiSensorViewer-SFML
14. RotatedBodyViewer-SFML
15. SimpleBodyViewer-SFML (default value in Dockerfile)
16. SimpleColorViewer-SFML
17. SimpleDepthViewer-SFML
18. SimpleStreamViewer-SFML
