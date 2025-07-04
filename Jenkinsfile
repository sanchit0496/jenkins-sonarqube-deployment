pipeline {
  agent any

  environment {
    SONAR_TOKEN = credentials('SONAR_TOKEN')
  }

  tools {
    nodejs 'node-18'
  }

  stages {
    stage('Install') {
      steps {
        bat 'npm ci'
      }
    }

    stage('Test + Coverage') {
      steps {
        bat 'npm test -- --coverage --passWithNoTests'
      }
    }

    stage('SonarQube Analysis') {
      steps {
        withSonarQubeEnv('My SonarQube Server') {
          bat 'npx sonar-scanner'
        }
      }
    }
  }
}
