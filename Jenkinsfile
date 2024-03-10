pipeline {
    agent any

    stages {
        stage('Test') {
            steps {
                withCredentials([[$class: 'VaultUsernamePasswordCredentialBinding', credentialsId: 'vault-jenkins', passwordVariable: 'PASSWORD', usernameVariable: 'USERNAME']]) {
                    sh 'echo $PASSWORD'
                }  
            }
        }

        stage('Test-1'){
            steps {
            script{
                def secrets = [
                    [
                        path: 'secrets/new-static-v2/creds/ansible', engineVersion: 2, secretValues: [
                            [envVar: 'ANSIBLE_KEY', vaultKey: 'ansible_key']
                        ]
                    ]
                ]

                def configuration = [
                    vaultUrl: 'http://m2-fedair.39.local:8200',
                    vaultCredentialId: 'vault-jenkins',
                    engineVersion: 2
                ]

                withVault([configuration: configuration, vaultSecrets: secrets]) {
                    def secretData = vaultRead(path: 'secrets/new-static-v2/creds/ansible/ansible_key')
                    sh 'echo "Vault KV Values"'
                    echo "All secrets: ${secretData.data}"
                }
            }
        }
        }
    }
}
