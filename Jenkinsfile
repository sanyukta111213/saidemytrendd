pipeline {
    agent any
    environment {
        PATH = "/opt/maven/bin:$PATH"
    }
    stages {
        stage('Build') {
            steps {
               
                sh 'mvn clean deploy -Dmaven.test.skip=true'
        }
      }
       
          stage('test') {
            steps {



                sh 'mvn surefire-report:report'


            }
        }        stage('SonarQube Analysis') {
            environment {
                scannerHome = tool 'sonar-scanner-tool'
            }
            steps {
                withSonarQubeEnv('sonar-server') {
                    sh "${scannerHome}/bin/sonar-scanner"
                }
            }
        }
    }
} 
