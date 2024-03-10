pipeline {
    agent any

    stages {
        stage('Test') {
            steps {
                withCredentials([VaultStringCredential(credentialsId: 'vault-jenkins', variable: 'username')]) {
                    sh 'echo Hello'
                }   
            }
        }
    }
}
