# install-docker-and-portainer_debian12

<h1>download Debian 12</h1>

### IMPORTANT

Download last version of Debian 12

### 1. update and install packages

```
sudo apt-get update sudo apt-get install ca-certificates curl gnupg
```

### 2. add docker's GPG key

```
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/debian/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg
```

### 3. setup repository

```echo \
  "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/debian \
  "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

### 4. update ur packages and install docker

```
sudo apt-get update
```

```
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

### 5. verify if docker is installed correctly

```
sudo docker run hello-world
```
