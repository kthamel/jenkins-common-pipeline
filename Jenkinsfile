pipeline {
    agent any

    stages {
        stage('Test') {
            steps {
                withCredentials([vaultStringCredential(credentialsId: 'vault-jenkins', variable: 'username')]) {
                    sh 'echo Hello'
                }   
            }
        }
    }
}
