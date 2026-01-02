pipeline {
    agent any
      tools {
        nodejs 'node'
     }
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

