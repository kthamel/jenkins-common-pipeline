@Library("jenkins-groovy-library") _
pipeline {
    agent any

    stages {
        stage('Hello Directly') {
            steps {
                withGroovy {
                    sh 'java --version'
                    sh 'groovy --version'
                    sh 'terraform --version'
                    sh 'aws --version'
                }
            }
        }

        stage('List AWS Resources') {
            steps {
                withCredentials([aws(accessKeyVariable: 'AWS_ACCESS_KEY_ID', credentialsId:'dba-user', secretKeyValueVariable: 'AWS_SECRET_ACCESS_KEY')]) {
                    sh  'aws s3 ls'
                }
            }
        }

        stage('Terraform Initialization') {
            steps {
                withGroovy {
                    tfinit()
                }
            }
        }

        stage('Terraform Validation') {
            steps {
                withGroovy {
                    tfvalidate()
                }
            }
        }

        stage('Terraform Plan') {
            steps {
                withGroovy {
                    tfplan()
                }
            }
        }

        stage('Terraform Apply') {
            steps {
                withGroovy {
                    tfapply()
                }
            }
        }
    }
}
