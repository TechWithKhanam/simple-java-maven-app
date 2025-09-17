pipeline {
    agent any
    
    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "Maven"
    }
    stages {
        stage('Code fetch from Github repo') {
            steps {
                echo 'Fetching the code'
                git branch: 'branch1', url: 'https://github.com/TechWithKhanam/simple-java-maven-app.git'
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
    }
}
