@Library("jenkins-groovy-library") _
pipeline {
    agent any

    stages {
        stage('Hello Directly') {
            steps {
                withGroovy {  
                    sh 'java --version'
                    sh 'groovy --version'
                }
            }
        }
        stage('Hello from Library') {
            steps {
                withGroovy {
                    helloWorld("Kushan","Tuesday")
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
        stage('Check Terraform version') {
            steps {
                withGroovy {
                    terraformInit()
                }
            }
        }
    }
}
