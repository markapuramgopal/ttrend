pipeline {
    agent {
        node {
            label 'maven-agent'
        }
    }

environment {
    PATH = "/opt/apache-maven-3.9.5/bin:$PATH"
}
    stages {
        stage('build'){
            steps {
                sh 'mvn clean deploy'
            }
        }
        stage('sonarqube analysis'){
            environment{
                scannerHome = tool 'sonarscanner'
            }
            steps{
                 withSonarQubeEnv('sonarqube-server') { // If you have configured more than one global server connection, you can specify its name
                 sh "${scannerHome}/bin/sonar-scanner"
                 }
            }
        }
    }
}    
