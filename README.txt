pipeline {
  agent {
    node {
      label "master"
    }
  }

  stages {
    stage("SonarQube analysis") {
       steps {
          script {
              def sonarScanner = tool name: 'SonarQube', type: 'hudson.plugins.sonar.SonarRunnerInstallation'
              bat "${sonarScanner}/bin/sonar-scanner -e -Dsonar.host.url=pipeline {
  agent {
    node {
      label "master"
    }
  }

  stages {
    stage("SonarQube analysis") {
       steps {
          script {
              def sonarScanner = tool name: 'SonarQube', type: 'hudson.plugins.sonar.SonarRunnerInstallation'
              bat "${sonarScanner}/bin/sonar-scanner -e -Dsonar.host.url=https://github.com/Debadutta-Pradhan/HappyTrip4.git"
            }
         }
      }
    }
  }
