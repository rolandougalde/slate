# Docker

Docker takes away repetitive, mundane configuration tasks and is used throughout the development lifecycle for fast, easy and portable application development – desktop and cloud. Docker’s comprehensive end to end platform includes UIs, CLIs, APIs and security that are engineered to work together across the entire application delivery lifecycle.

## Install Docker

> Install from Docker official site:

```shell
sudo apt update
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
```

## Post install configuration

> Running docker as non root user:

```shell
sudo groupadd docker
sudo usermod -aG docker $USER
newgrp docker
```

> Verify that you can run docker commands without sudo.

```shell
docker run hello-world
sudo chown "$USER":"$USER" /home/"$USER"/.docker -R
sudo chmod g+rwx "$HOME/.docker" -R
```

> Enable start on boot service.

```shell
sudo systemctl enable docker.service
sudo systemctl enable containerd.service
```

> Disable start on boot service.

```shell
sudo systemctl disable docker.service
sudo systemctl disable containerd.service
```
