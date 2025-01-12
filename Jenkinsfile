pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                // Run the Maven command
                sh 'mvn clean deploy'
            }
        }
    }
}
