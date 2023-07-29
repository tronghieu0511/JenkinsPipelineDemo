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
                sshagent(['ssh-creds']) {
                sh 'ssh -o StrictHostKeyChecking=no -l hieu 192.168.0.10 uname -a touch ~/.ssh/textJenkins.txt'
                }        
            }
        }
    }
}
