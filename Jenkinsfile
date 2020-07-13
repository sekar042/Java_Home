pipeline {
    agent any
    tools {
        maven 'maven3'
    }
    stages {
        stage('Build'){
            steps{
                sh label: '', script: 'mvn clean package'
            }

        }
    }
}
