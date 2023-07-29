pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploing'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing'
            }
        }
        stage('Release') {
            steps {
                echo 'Releasing'
            }
        }
        stage('SSH server'){
            steps {
              sshagent(credentials: ['ssh-remote'], ignoreMissing: true) {
                sh 'ssh -o StrictHostKeyChecking=no -l hieu 192.168.0.10 touch ~/.ssh/test.txt'
                }          
            }
        }
    }
}
