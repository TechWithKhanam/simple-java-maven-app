pipeline {
    agent { label 'slave1' }
    
    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "Maven"
    }
    stages {
        stage('Code fetch from Github repo') {
            steps {
                echo 'Fetching the code'
                git branch: 'testing-branch', url: 'https://github.com/TechWithKhanam/simple-java-maven-app.git'
            }
        }
         stage('Maven build') {
            steps {
                echo 'building the code'
               sh "mvn clean package"
            }
        }
        stage('testing code') {
            steps {
                echo 'testing the code'
               sh "mvn test"
            }
        }
	stage('Archiving the artifacts') {
            steps {
                echo 'archiving the artifact'
               archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
            }
        }
    }
}
