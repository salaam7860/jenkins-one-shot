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
### Console Output
``` 
Started by user bee
[Pipeline] Start of Pipeline
[Pipeline] node
Running on Jenkins in /var/lib/jenkins/workspace/cicd
[Pipeline] {
[Pipeline] stage
[Pipeline] { (Hello)
[Pipeline] echo
Hello World
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Create directory)
[Pipeline] sh
+ mkdir -p devops
[Pipeline] }
[Pipeline] // stage
[Pipeline] }
[Pipeline] // node
[Pipeline] End of Pipeline
Finished: SUCCESS
```