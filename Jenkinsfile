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
                sh 'ssh -o StrictHostKeyChecking=no -l hieu 192.168.0.10 touch /home/hieu/.ssh/test.txt'
                }          
            }
        }
        stage('SSH Publish'){
            steps {
              sshPublisher(publishers: [sshPublisherDesc(configName: 'Server linux', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: 'cp readme.txt TestSSH.txt', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '', remoteDirectorySDF: false, removePrefix: '', sourceFiles: 'readme.txt')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
                }          
            }
        }
    }

