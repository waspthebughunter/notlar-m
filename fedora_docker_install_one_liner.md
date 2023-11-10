one liner for installation of docker top of fedora linux

```
sudo dnf -y install dnf-plugins-core && sudo dnf config-manager --add-repo https://download.docker.com/linux/fedora/docker-ce.repo && sudo dnf install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin 
```

run docker without sudo

```
sudo groupadd docker && sudo usermod -aG docker $USER && newgrp docker
```

u can now use docker without sudo

test:
```
docker run hello-world
```
