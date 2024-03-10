pipeline {
    agent any

    stages {
        stage('Test') {
            steps {
                withCredentials([vaultString(credentialsId: 'vault-jenkinsx', variable: '')]) {
                    sh 'echo Hello'
                }   
            }
        }
    }
}
