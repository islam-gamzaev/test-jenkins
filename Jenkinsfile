pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'pwd && ls -lh'
                echo 'Build some application'
            }
        }
        stage('Test') {
            steps {
                echo 'Test some application'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploy some application'
            }
        }
    }
 }