# Lab 2a. Docker Introduction

## Overview

This guide will show you how to pull a Docker image, and run a new container
from that image. All commands in this 

1. First, pull the hello-world docker image.

    You can interact with Docker on the command line using the `docker` command.

    The `docker` command has a number of sub-commands that you specify like so: `docker <subcommand>`.

    In this case, we're going to run the Docker pull subcommand which will download the hello-world image from Docker Hub.

    ```
    docker pull hello-world
    ```

    You should see output similar to the following:

    ```
    Using default tag: latest
    latest: Pulling from library/hello-world
    2db29710123e: Pull complete 
    Digest: sha256:6d60b42fdd5a0aa8a718b5f2eab139868bb4fa9a03c9fe1a59ed4946317c4318
    Status: Downloaded newer image for hello-world:latest
    docker.io/library/hello-world:latest
    ```

    Now the `hello-world` image is on your computer. In the next step, we'll
    actually run the application inside the image.

2. Create a new container and run it.

    To create a new container, we use the `docker run` subcommand. With `docker run`, we'll also specify `--rm`.  `--rm` tells Docker to delete the container after the program inside the container terminates. If `--rm` is left off, Docker will keep the container around after the application terminates. Unless you have a reason to keep the container around, its generally a good idea to delete it once its done because containers do use disk space.

    ```
    docker run --rm hello-world
    ```

    You should see output similar to the following:

    ```
    Hello from Docker!
    This message shows that your installation appears to be working correctly.

    To generate this message, Docker took the following steps:
     1. The Docker client contacted the Docker daemon.
     2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
        (amd64)
     3. The Docker daemon created a new container from that image which runs the
        executable that produces the output you are currently reading.
     4. The Docker daemon streamed that output to the Docker client, which sent it
        to your terminal.

    To try something more ambitious, you can run an Ubuntu container with:
     $ docker run -it ubuntu bash

    Share images, automate workflows, and more with a free Docker ID:
     https://hub.docker.com/

    For more examples and ideas, visit:
     https://docs.docker.com/get-started/
    ```

    Congratulations, you've just run your first container! Now in the next lab, we'll create our own image.

# Lab 2b. Build an Image and Analyze in Mayhem.

