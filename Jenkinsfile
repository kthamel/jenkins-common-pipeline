/* groovylint-disable LineLength, NestedBlockDepth */
@Library("jenkins-groovy-library") _
pipeline {
    agent any {
        withCredentials([aws(accessKeyVariable: 'AWS_ACCESS_KEY_ID', credentialsId:'dba-user', secretKeyValueVariable: 'AWS_SECRET_ACCESS_KEY')]) {
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
}
