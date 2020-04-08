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
    stage('Compile') { // Compile and do unit testing
      steps {
        // run Gradle to execute compile and unit testing
        //sh "./gradlew clean build"
        gradle('clean build')
      }
    }
  }
}