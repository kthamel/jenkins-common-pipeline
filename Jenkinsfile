pipeline {
    agent any

    stages {
        stage('Test') {
            steps {
                withCredentials([vaultString(credentialsId: 'vault-jenkins', variable: 'username')]) {
                    sh 'echo Hello'
                }   
            }
        }
    }
}
