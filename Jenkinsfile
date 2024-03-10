pipeline {
    agent any

    stages {
        stage('Invoke_Develop_Credentials') {
            steps {
                withCredentials([[$class: 'VaultUsernamePasswordCredentialBinding', credentialsId: 'vault-jenkins', passwordVariable: 'PASSWORD', usernameVariable: 'USERNAME']]) {
                    sh 'echo Stage Passed'
                }  
            }
        }

        stage('Invoke_Ansible_Credentials') {
            steps {
                withCredentials([vaultString(credentialsId: 'ansible_key', variable: '')]) {
                    sh 'echo Stage Passed'
                } 
            }
        }
    }
}
