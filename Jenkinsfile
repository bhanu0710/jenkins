pipeline {
    agent any
    tools {
        nodejs 'node'
     }
    stages {
        stage('Installing Dependencies') {
            steps {
                sh 'npm install --no-audit'
            }
        }
        stage('NPM Dependency Audit') {
            steps {
                sh '''
                   npm audit --audit-level=critical
                   echo $?
                '''
                
            }

            
        }  
        stage('Unit Testing') {
            steps {
                sh 'npm test'
                   
                
            }
            
            
        } 
        
    }
}
