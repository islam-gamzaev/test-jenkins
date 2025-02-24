pipeline {
    agent any
    environment {
        EXAMPLE_VAR = """
            ${sh(returnStdout = true, script = 'echo "YOUR EXAMPLE VAR"')}
        """
        EXIT_STATUS = """
            ${sh(returnStatus = true, script = 'exit 1')}
        """
    }
    stages {
        stage('Build') {
            steps {
                sh 'pwd && ls -lh'
                echo 'Build some application with EXAMPLE_VAR="${env.EXAMPLE_VAR}"'
            }
        }
        stage('Test') {
            steps {
                echo 'Test some application with result EXIT_STATUS="${env.EXIT_STATUS}"'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploy some application'
            }
        }
    }
 }