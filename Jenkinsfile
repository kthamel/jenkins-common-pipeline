pipeline {
    agent any

    stages {
        withVault(configuration: [disableChildPoliciesOverride: false, engineVersion: 2, prefixPath: 'secrets/new-static-v2/creds /develop', skipSslVerification: true, timeout: 60, vaultCredentialId: 'vault-jenkins-role', vaultUrl: 'http://172.16.127.128:8200'])
        stage('Test') {
            steps {
                sh '''
                echo $username $password
                '''
            }
        }
    }
}
