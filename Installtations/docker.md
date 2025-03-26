# Docker Installation

```
sudo apt update
sudo apt install docker.io
```
## Docker Compose install 
### Scenario two: Install the Docker Compose plugin

- [Using Docker's repository](https://docs.docker.com/compose/install/linux/#install-using-the-repository)

- [Downloading and installing manually](https://docs.docker.com/compose/install/linux/#install-the-plugin-manually)

### Install the Docker Compose standalone

```
sudo curl -SL https://github.com/docker/compose/releases/download/v2.34.0/docker-compose-linux-x86_64 -o /usr/local/bin/docker-compose
```

**Apply executable permissions to the standalone binary in the target path for the installation.**


``` 
sudo chmod +x /usr/local/bin/docker-compose
```
**If the command docker-compose fails after installation, check your path. You can also create a symbolic link to /usr/bin or any other directory in your path. For example:**

```
sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose
```

### Add the User to the Docker Group
```
sudo usermod -aG docker ${USER}
```

### Another solution is to change the ownership of the Docker socket to the current user.

```bash
sudo chown ${USER}:docker /var/run/docker.sock

```
## If not working:
### Check Docker Socket Permissions
```bash
ls -l /var/run/docker.sock
```
**If the group for /var/run/docker.sock is not docker, or if the permissions do not allow the Jenkins user to access it, you can update the permissions with:**

```bash
sudo chmod 666 /var/run/docker.sock
```
###  Restart Jenkins and Docker
```bash
sudo systemctl restart jenkins
sudo systemctl restart docker

```
### Test Docker Access
```bash
sudo -u jenkins docker ps
```