pipeline {
    agent any
    tools {
        maven 'maven3'
    }
    stages{
        stage('Build'){
            steps{
                sh script: 'mvn clean package'
            }
        }
        stage('Upload war file into nexus'){
            steps{
                nexusArtifactUploader artifacts: [
                    [
                        artifactId: 'simple-app', 
                        classifier: '', 
                        file: 'target/simple-app-1.0.0.war', 
                        type: 'war'
                    ]
                ], 
                credentialsId: 'nexus3', 
                groupId: 'in.javahome', 
                nexusUrl: '172.31.3.163', 
                nexusVersion: 'nexus2', 
                protocol: 'http', 
                repository: 'http://52.14.160.207:8081/repository/simpleapp-release/', 
                version: '1.0.0'
            }
        }
    }
}
