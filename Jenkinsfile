pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('new'){
           steps { 
               script {
                  sh 'node -v'
                   }
                }
            }
    }
}

