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
        stage('Docker build') {
            steps {
                sh 'docker build -t bhanu0710/project:$GIT_COMMIT .'
                   
                
            }
            
            
        } 
        stage('Trivy Vulnerability Scanner') {
            steps {
                sh '''
                   trivy image bhanu0710/project:$GIT_COMMIT \
                     --severity CRITICAL \
                     --exit-code 1 \
                     --quiet \
                     --format json -o trivy-image-critical-results.json
                '''
                
            }

            
        }
        
    }
}
