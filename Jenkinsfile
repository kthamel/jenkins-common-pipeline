pipeline {
    agent any

    stages {
        withVault(configuration: [disableChildPoliciesOverride: false, timeout: 60, vaultCredentialId: 'vault-jenkins', vaultUrl: 'http://172.16.127.128:8200']) {
        stage('stage-01') {
            steps {
                echo 'Hello World 01'
                }
            }
        }    
    }
}
