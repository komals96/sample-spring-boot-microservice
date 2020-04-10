// Scripted Pipeline with stages
pipeline {
  agent { label 'master' }
  stages {
    stage('Source') { // Get code
      steps {
        // get code from our Git repository
        git 'https://github.com/vinayaka-rs/sample-spring-boot-microservice.git'
      }
    }
    stage('Build and Archive') { // Compile and do unit testing
      steps {
        // run Gradle to execute compile and unit testing
        sh "chmod +x gradlew"
        sh "./gradlew clean build"
      }
      post {
        success {
          archiveArtifacts artifacts: 'build/**/**/*', fingerprint: true
        }
      }
    }
  }
}