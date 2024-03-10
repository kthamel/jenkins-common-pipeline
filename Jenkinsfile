pipeline {
    agent any

    stages {
        stage('Test') {
            steps {
                withCredentials([vaultString(credentialsId: '', variable: 'vault-jenkins')]) {
                    sh 'echo Hello'
                }   
            }
        }
    }
}
