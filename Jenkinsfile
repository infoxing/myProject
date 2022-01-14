pipeline {
  agent { label 'linux' }
  tools {
    maven 'maven-3.8.4'
  }
  stages {
    stage('checkout') {
      steps {
        git 'https://github.com/infoxing/myProject.git'
      }
    }
    stage('Build') {
      steps {
        sh 'mvn clean compile'
      }
    }
    stage('Test') {
      steps {
        sh 'mvn test'
        junit '**/target/surefire-reports/TEST-*.xml'
      }
    }
    stage('Package') {
      steps {
        sh 'mvn package'
      }
    }
  }
}
