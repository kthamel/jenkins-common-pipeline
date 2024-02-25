pipeline {
    agent any

    stages {
        withVault(configuration: [disableChildPoliciesOverride: false, timeout: 60, vaultCredentialId: 'vault-jenkins', vaultUrl: 'http://m2-air.prod-vault.local:8200']) {
        stage('Stage-01') {
            steps {
                echo 'Hello World 01'
                }
            }
        }    
    }
}
