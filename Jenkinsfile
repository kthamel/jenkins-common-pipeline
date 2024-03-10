pipeline {
    agent any

    stages {
        stage('Invoke_Credentials') {
            steps {
                withCredentials([[$class: 'VaultUsernamePasswordCredentialBinding', credentialsId: 'vault-jenkins', passwordVariable: 'PASSWORD', usernameVariable: 'USERNAME']]) {
                    sh 'echo $PASSWORD'
                }  
            }
        }
    }
}
