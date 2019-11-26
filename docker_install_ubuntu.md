## Docker installation in ubuntu 18.04  


### Update the apt package

```sh
sudo apt-get update
```

### Remove any old insatllation

```sh
sudo apt-get remove docker docker-engine docker.io containerd runc
```

### somthing something

```sh
sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common
```

### Add Docker’s official GPG key

```sh
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo apt-key fingerprint 0EBFCD88
```

### set up stable repository

```sh
sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"
```

### Update the apt package again

```sh
sudo apt-get update
```

### finally install

```sh
sudo apt-get install docker-ce docker-ce-cli containerd.io
```

### verify the install

```sh
sudo docker run hello-world
```
