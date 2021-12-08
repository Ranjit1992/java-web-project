pipeline {
    agent any
    stages {
        stage('Build'){
            steps {
                bat "mvn clean package"
            }
        }
        stage('Deploy'){
            steps {
                deploy adapters: [
                    tomcat8(credentialsId: '0b8a93ec-62f0-4295-9eb7-7bfa091c0152', 
                    path: '', 
                    url: 'http://localhost:8091/')], 
                contextPath: 'javawebapp',
                war: '**/java-web-project.war'
            }
        }
    }
}
