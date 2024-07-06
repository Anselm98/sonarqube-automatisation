node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    def scannerHome = tool 'SonarScanner'
    withSonarQubeEnv('sonarqubeserver') { // Ensure this matches your Jenkins SonarQube server name
      sh "${scannerHome}/bin/sonar-scanner -Dsonar.projectKey=PHP-Project -Dsonar.sources=. -Dsonar.host.url=http://sonarqube:9000 -Dsonar.login=sgp_5440bce49de8c93a8923541e2c770470bb90e414"
    }
  }
}

