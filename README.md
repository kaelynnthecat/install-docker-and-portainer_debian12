# install-docker-and-portainer_debian12

<h1>download Debian 12</h1>

### update and install packages

<p>sudo apt-get update
sudo apt-get install ca-certificates curl gnupg</p>

# add docker's GPG key

<p>sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/debian/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg</p>

# setup repository

<p>echo \
  "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/debian \
  "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null</p>

  # update ur packages and install docker

  <p>sudo apt-get update</p>

  <p>sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin</p>

  # verify if docker is installed correctly

  <p>sudo docker run hello-world</p>
