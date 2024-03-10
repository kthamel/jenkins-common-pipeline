pipeline {
    agent any

    stages {
        stage('Invoke_Develop_Credentials') {
            steps {
                withCredentials([[$class: 'VaultUsernamePasswordCredentialBinding', credentialsId: 'vault-jenkins', passwordVariable: 'PASSWORD', usernameVariable: 'USERNAME']]) {
                    sh 'echo $PASSWORD'
                }  
            }
        }

        stage('Invoke_Ansible_Credentials') {
            steps {
                withCredentials([[$class: 'VaultSSHUserPrivateKey', credentialsId: 'ansible_key', VaultSSHUserPrivateKey: 'PRIVATE_KEY']]) {
                    sh 'echo $PRIVATE_KEY'
                }  
            }
        }
    }
}
