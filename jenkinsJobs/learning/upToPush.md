# Pipeline with dockerHub Credentials 
## One way.
```bash
pipeline {
    
    agent {label 'agentx'}
    
    stages {
        
        stage('Code') {
            steps {
                echo 'This is coping the code.'
                git url: "https://github.com/salaam7860/django-notes.git", branch:"main"
                echo "The code has been successfully cloned"
            }
        }
        
        stage('Build') {
            steps {
                echo 'This is building the code'
                sh 'whoami'
                sh 'docker build -t notes-app:latest .'
            }
            
        }
        
        stage('Push to docker-hub') {
            steps {
                echo 'This is pushing the image to dockerhub'
                withCredentials([usernamePassword(credentialsId: "dockerHubCred", passwordVariable: "dockerHubPass", usernameVariable: "dockerHubUser")]) {
                    sh """
                        #!/bin/bash
                        cat /home/dragon/var/ex.txt | docker login -u ${dockerHubUser} --password-stdin
                        docker image tag notes-app:latest ${dockerHubUser}/notes-app:latest
                        docker push ${dockerHubUser}/notes-app:latest
                    """
                }
            }
        }
        
        stage('Deploy') {
            steps {
                echo 'This is deploying the code.'
                sh 'docker-compose up -d'
            }
        }
        
    }
}
```

## Second way.
```bash
pipeline {
    
    agent {label 'agentx'}
    
    stages {
        
        stage('Code') {
            steps {
                echo 'This is coping the code.'
                git url: "https://github.com/salaam7860/django-notes.git", branch:"main"
                echo "The code has been successfully cloned"
            }
        }
        
        stage('Build') {
            steps {
                echo 'This is building the code'
                sh 'whoami'
                sh 'docker build -t notes-app:latest .'
            }
            
        }
        
        stage('Push to docker-hub') {
            steps {
                echo 'This is pushing the image to dockerhub'
                withCredentials([usernamePassword(credentialsId: "dockerHubCred", passwordVariable: "dockerHubPass", usernameVariable: "dockerHubUser")]) {
                    sh "docker login -u ${dockerHubUser} -p ${dockerHubPass}"
                    sh "docker image tag notes-app:latest ${dockerHubUser}/notes-app:latest"
                    sh "docker push ${dockerHubUser}/notes-app:latest"
              
                }
            }
        }
        
        stage('Deploy') {
            steps {
                echo 'This is deploying the code.'
                sh 'docker-compose up -d'
            }
        }
        
    }
}
```