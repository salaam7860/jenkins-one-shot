# Add the Jenkins user to the Docker group
 
 ### Solution 1:
 - Run the following command:
    ```
    sudo usermod -aG docker dragon
    ```
### Solution 2:
Change the ownership of the Docker socket
  
  - Run the following command:
  
     ```
     sudo chown dragon:docker /var/run/docker.sock
     ```
### Solution 3:
Use the docker command with sudo.

- Modify your Jenkinsfile or shell script:
    ```
    pipeline {
    // ...
    stage('Build Docker image') {
        steps {
            sh 'sudo docker build -t notes-app:latest .'
            }
        }
    // ...
    }
    ```
