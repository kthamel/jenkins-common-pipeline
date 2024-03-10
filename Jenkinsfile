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
                withCredentials([[$class: 'VaultSSHUserPrivateKeyBinding', credentialsId: 'ansible_key', privateKeyVariable: 'PRIVATE_KEY', usernameVariable: 'USERNAME']]) {
                    sh 'echo $ANSIBLE_KEY'
                }  
            }
        }
    }
}
