node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    def scannerHome = tool 'SonarScanner'
    withSonarQubeEnv('sonarqubeserver') { 
      sh "${scannerHome}/bin/sonar-scanner"
    }
  }
}

