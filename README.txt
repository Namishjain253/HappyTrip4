node {
  stage('SCM') {
    git 'https://github.com/Debadutta-Pradhan/HappyTrip4.git'
  }
  stage('SonarQube analysis') {
    withSonarQubeEnv(credentialsId: 'd96363fe0bce1e5a3febf67cb9f42f755212a841', installationName: 'Secret text') { // You can override the credential to be used
      sh 'mvn org.sonarsource.scanner.maven:sonar-maven-plugin:3.6.0.1398:sonar'
    }
  }
}

