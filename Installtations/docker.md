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
curl -SL https://github.com/docker/compose/releases/download/v2.34.0/docker-compose-linux-x86_64 -o /usr/local/bin/docker-compose
```

**Apply executable permissions to the standalone binary in the target path for the installation.**


``` 
chmod +x /usr/local/bin/docker-compose
```
**If the command docker-compose fails after installation, check your path. You can also create a symbolic link to /usr/bin or any other directory in your path. For example:**

```
sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose
```