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
    }
}
