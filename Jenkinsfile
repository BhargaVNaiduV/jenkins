pipeline {
    agent any
    }
tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven '3.9.0'
    }
    stages {
        stage('Test') {
            steps {
                git 'https://github.com/jglick/simple-maven-project-with-tests.git'
                sh 'mvn test'
            }
        }
    }
