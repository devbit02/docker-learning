# Docker Commands

See all the containers currently running.

```bash
docker ps
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES
```
In this case nothing is running since we havent started any containers yet.

## Run Ubuntu in interactive mode

Run the following command:
```bash
docker run -it ubuntu /bin/bash
```
Which should show the following output:

```bash
Unable to find image 'ubuntu:latest' locally
latest: Pulling from library/ubuntu
84ed7d2f608f: Pull complete
be2bf1c4a48d: Pull complete
a5bdc6303093: Pull complete
e9055237d68d: Pull complete
Digest: sha256:868fd30a0e47b8d8ac485df174795b5e2fe8a6c8f056cc707b232d65b8a1ab68
Status: Downloaded newer image for ubuntu:latest
```
This pulls the Ubuntu image from the remote repository and runs the container in interactive mode `-i` using the `/bin/bash` command.

To get out of the container type `exit` in the terminal.  You will then go back to you command line.

Let's run the `docker ps` command again.

```bash
docker ps
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES
```
Still nothing showing.  Why?  Becuase the `-t` command added to our command early told Docker to terminate the container when the process was completed.  In this case, the `bash` process was completed when we typed `exit` to get out of the container.

Now type `docker ps -a` to see what happens:

```bash
docker ps -a
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS                       PORTS               NAMES
2f13f15ca8a3        ubuntu              "/bin/bash"         17 minutes ago      Exited (127) 4 minutes ago                       festive_hawking
```
Now we see something.  The `-a` tells the `docker ps` command to show all containers, not just the running ones.

Another way to show the containers is the more explicit command `docker container ls -a`, which will product the exact same results as `docker ps -a`.

```bash
docker container ls -a
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS                       PORTS               NAMES
2f13f15ca8a3        ubuntu              "/bin/bash"         21 minutes ago      Exited (127) 8 minutes ago                       festive_hawking
```