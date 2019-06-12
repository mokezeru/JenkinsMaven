pipeline {
    agent any 
    stages {
        stage('Clone repo and Clean it') { 
            steps {
               bat "mvn clean"
            }
        }
        stage('Test') { 
            steps {
                bat "mvn test"
            }
        }
        stage('Deploy') { 
            steps {
                bat "mvn package"
            }
        }
    }
}