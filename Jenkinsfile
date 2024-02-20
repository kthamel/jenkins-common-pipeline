// @Library("jenkins-groovy-library") _
pipeline {
    agent any

    stages {
        stage('Hello Directly') {
            steps {
                withGroovy {
                    sh 'java --version'
                }
            }
        }
    }
        
}
