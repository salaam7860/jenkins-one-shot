# Jenkins One Shot

## Installation
### Pre-requisite 
- Java openjdk-17-jdk

```
sudo apt update
sudo apt install openjdk-17-jdk
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
sudo systemctl --full status jenkins
```

**You can start the Jenkins service with the command:**
```
sudo systemctl start jenkins
```
**You can enable the Jenkins service to start at boot with the command.**
```
sudo systemctl enable jenkins
```
###  To change the Jenkins default port from 8080 to any port, you can follow these steps:

- Open the Jenkins configuration file in a text editor:
  ```
  sudo nano /etc/default/jenkins
  ```
- Look for the HTTP_PORT variable and change its value to Any:
    ```
    HTTP_PORT=8081
    ```
- Save and close the file.
- Restart the Jenkins service:
  ```
  sudo service jenkins restart
  ```


