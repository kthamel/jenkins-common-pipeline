pipeline {
    agent any

    stages {
        stage('Test') {
            steps {
                withVault(configuration: [disableChildPoliciesOverride: false, engineVersion: 2, skipSslVerification: true, timeout: 60, vaultCredentialId: 'vault-jenkins-role', vaultUrl: 'http://m2-fedair.39.local:8200'], vaultSecrets: [[engineVersion: 2, path: 'secrets/new-static-v2/creds/develop']]){
                    sh 'echo $username $password'
                }
            }
        }
    }
}
