pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven '3.9.0'
    }

    stages {
        stage('Code checkOut') {
            steps {
                git 'https://github.com/jglick/simple-maven-project-with-tests.git'
            }
        }

        stage('Compile') {
            steps {
                echo '--- Step 1: Cleaning ---'
                sh 'mvn clean'

                echo '--- Step 2: Updating Dependencies ---'
                sh 'mvn dependency:resolve'

                echo '--- Step 3: Compiling ---'
                sh 'mvn compile'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
    }
}
