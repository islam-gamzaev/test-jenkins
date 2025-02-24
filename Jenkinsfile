pipeline {
    agent any
    environment {
        EXAMPLE_VAR = """
            ${sh(returnStdout: true, script: 'echo "YOUR EXAMPLE VAR"')}
        """
        EXIT_STATUS = """
            ${sh(returnStatus: true, script: 'exit 1')}
        """
    }
    stages {
        stage('Creds') {
            steps {
                withCredentials(bindings: [sshUserPrivateKey(credentialsId: 'github-id',
                                                             keyFileVariable: 'GITHUB_PKEY_VAR',
                                                             passphraseVariable: 'GITHUB_PASSPHRASE_VAR',
                                                             usernameVariable: 'GITHUB_USERNAME_VAR')]) {
                    sh 'env'
                }
            }
        }
        stage('Build') {
            steps {
                sh 'pwd && ls -lh'
                echo "Build some application with EXAMPLE_VAR=${env.EXAMPLE_VAR.trim()}"
            }
        }
        stage('Test') {
            steps {
                echo "Test some application with result EXIT_STATUS=${env.EXIT_STATUS.trim()}"
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploy some application'
            }
        }
    }
 }