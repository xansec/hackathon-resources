# Lab 2a. Docker Introduction

This lab will show you how to pull a Docker image, and run a new container
from that image.

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

# Lab 2b. Build an Image and Analyze in Mayhem

This lab will show you how to build a Docker image for a toy program, push it to a Docker registry, and then use Mayhem to analyze the toy program in the image.

1. First, we need to setup Docker to enable pushing new images for a later step.

    a. Navigate to https://github.com.

    b. Click on your user account icon to reveal a drop down menu.

       ![Account Drop Down](assets/images/github-user-icon.png)

    c. Click on settings in the drop down menu.

       ![Settings](assets/images/gh-settings.png)

    d. On the left side of the settings page, select "Developer Settings."

       ![Developer Settings](assets/images/gh-dev-settings.png)

    e. On the developer settings page, select "Personal Access Tokens".

       ![Select PAT](assets/images/gh-pat.png)

    f. Click create new token.

       ![Create New PAT](assets/images/gh-gen-new-token.png)

    g. Enter a note for the token, and check the repo, workflow, write:packages, and delete:packages scopes.

       ![Select PAT Scopes](assets/images/gh-new-pat-scopes.png)

    h. Scroll to the bottom and click "Generate New Token".

       ![Gen New Token](assets/images/gh-gen-new-token.png)

    i. Click the copy button to copy the token to your clipboard.

       ![Copy Token](assets/images/gh-copy-token.png)

    j. Back on the command-line, we'll use the `docker login` command to login to the GitHub container registry.

        ```
        docker login -u <Your GitHub Username> ghcr.io
        ```

        When prompted for a password, paste your personal access token (PAT) that you copied in the previous step. Note the token will not echo. After pasting, press enter.

        You should see something similar to the following:

        ```
        Password: 
        WARNING! Your password will be stored unencrypted in /home/nathan/.docker/config.json.
        Configure a credential helper to remove this warning. See
        https://docs.docker.com/engine/reference/commandline/login/#credentials-store

        Login Succeeded
        ```

1. First, we need to clone the hackathon-resources repo and enter the "lab2b" directory.

    ```
    git clone https://github.com/makesoftwaresafe/hackathon-resources.git
    cd hackathon-resources/lab2b/
    ```

2. List the files in the lab2b directory:

    ```
    ls
    ```

    You should see the following:

    ```
    Dockerfile
    Mayhemfile
    fuzzme.c
    ```
    
    
