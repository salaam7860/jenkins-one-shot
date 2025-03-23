# Jenkins One Shot

## Installation
### Pre-requisite 
- Java openjdk-21-jdk

```
sudo apt update
sudo apt install openjdk-21-jdk
```
### Jenkins Installation Debian/Ubuntu
```
sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \
  https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
echo "deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc]" \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins
```
### Start Jenkins
**You can check the status of the Jenkins service using the command:**
```
sudo systemctl status jenkins
```

**You can start the Jenkins service with the command:**
```
sudo systemctl start jenkins
```
**You can enable the Jenkins service to start at boot with the command.**
```
sudo systemctl enable jenkins
```




