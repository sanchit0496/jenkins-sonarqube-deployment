pipeline {
  agent any

  environment {
    SONAR_TOKEN = credentials('SONAR_TOKEN')
  }

  tools {
    nodejs 'node-18'
  }

  stages {
    stage('Checkout') {
      steps {
        git url: 'https://github.com/sanchit0496/jenkins-sonarqube-deployment.git', branch: 'main'
      }
    }

    stage('Install Dependencies') {
      steps {
        sh 'npm ci'
      }
    }

    stage('Run Tests with Coverage') {
      steps {
        sh 'npm test -- --coverage --watchAll=false'
      }
    }

    stage('SonarQube Analysis') {
      steps {
        withSonarQubeEnv('My Sonar') {
          sh 'npx sonar-scanner'
        }
      }
    }

    stage('Quality Gate') {
      steps {
        timeout(time: 2, unit: 'MINUTES') {
          waitForQualityGate abortPipeline: true
        }
      }
    }
  }
}
