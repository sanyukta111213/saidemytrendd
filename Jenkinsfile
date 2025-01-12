pipeline {
    agent any
    environment {
          PATH = "/opt/maven/bin:$PATH"
}

    stages {
        stage ("build") {
          steps {
              sh 'mvn clean deploy'
           }
  }
          stage ("sonarQube analysis") {
             environment {
                scannerHome = tool 'sonar-scanner-tool'
           }
                 
            steps{
               withSonarQubeEnv('sonar-server') {

                 sh "${scannerHome}/bin/sonar-scanner"
 
              }
        }
     }
  } 
 } 
