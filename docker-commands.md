# Docker Commands

```bash
docker ps
```

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