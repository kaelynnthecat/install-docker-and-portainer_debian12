# install-docker-and-portainer_debian12

<h1>download Debian 12</h1>

### IMPORTANT

Download last version of Debian 12

### 1. update and install packages

```
sudo apt-get update
sudo apt-get install ca-certificates curl gnupg
```

### 2. add docker's GPG key

```
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/debian/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg
```

### 3. setup repository

```
echo \
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

<h1>install portainer</h1>

### create volume for portainer

```
docker volume create portainer_data
```

### install portainer

> Community Edition

```
docker run -d -p 8000:8000 -p 9443:9443 --name portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce:latest
```

> Business Edition

```
docker run -d -p 8000:8000 -p 9443:9443 --name portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ee:latest
```

### login portainer

3. login to portainer
 
 ```
 ip a
 ```

 copy ur ipv4 address and paste to ur browser w/ port (9443)<br>
 <i>example: 192.168.1.55:9443</i>
