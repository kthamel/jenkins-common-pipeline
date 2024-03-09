pipeline {
    agent any

    stages {
        stage('Test') {
            steps {
                withVault(configuration: [disableChildPoliciesOverride: false, engineVersion: 2, prefixPath: 'new-static-v2/creds', skipSslVerification: true, timeout: 60, vaultCredentialId: 'vault-jenkins-role', vaultUrl: 'http://m2-fedair.39.local:8200'], vaultSecrets: [[engineVersion: 2, path: 'develop']]){
                    sh 'echo Hello World'
                }
            }
        }
    }
}
