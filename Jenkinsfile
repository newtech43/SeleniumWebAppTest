node('new43') {
// Delete the workspace
//deleteDir()
     
stage('Retrieve source code') {
    checkout scm
    }
     stage('Maven Build') {
        sh "mvn clean package -Dbuild.number=${BUILD_NUMBER}"
      }
     stage('SonarQube analysis') {
    // requires SonarQube Scanner 2.8+
    def scannerHome = tool 'SonarQube Scanner 2.8';
    withSonarQubeEnv('My SonarQube Server') {
      sh "${scannerHome}/bin/sonar-scanner"
     }
    }
}
