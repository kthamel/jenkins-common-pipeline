pipeline {
    agent any

    stages {
        stage('Test') {
            steps {
                withVault(configuration: [disableChildPoliciesOverride: false, engineVersion: 2, prefixPath: 'secrets/new-static-v2/creds/develop', skipSslVerification: true, timeout: 60, vaultCredentialId: 'vault-jenkins-role', vaultUrl: 'http://m2-fedair.39.local:8200']){
                    sh '''
                    echo $username $password
                    '''
                }
            }
        }
    }
}
