# First Pipeline 

```
pipeline {
    agent any
    
    stages {
        
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        
        stage('Create directory') {
            steps {
                sh "mkdir -p devops"
            }
        }
    }
    
```