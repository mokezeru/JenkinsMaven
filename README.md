#Pipeline Declarative script
pipeline {
    agent any 
    stages {
        stage('Clone repo and Clean it') { 
            steps {
                bat "rmdir /Q /S JenkinsMaven"
                bat "git clone https://github.com/mokezeru/JenkinsMaven.git"
                bat "mvn clean -f JenkinsMaven"
            }
        }
        stage('Test') { 
            steps {
                bat "mvn test -f JenkinsMaven"
            }
        }
        stage('Deploy') { 
            steps {
                bat "mvn package -f JenkinsMaven"
            }
        }
    }
}