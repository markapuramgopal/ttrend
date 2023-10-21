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
                echo '------------------- Build Started -------------'
                sh 'mvn clean deploy'
                echo '------------------- Build Completed -------------'
            }
        }
