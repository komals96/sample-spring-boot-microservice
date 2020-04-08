// Scripted Pipeline with stages
node ('master') {
  stage('Source') { // Get code
    // get code from our Git repository
    git 'https://github.com/vinayaka-rs/sample-spring-boot-microservice.git'
  }
  stage('Compile') { // Compile and do unit testing
    // run Gradle to execute compile and unit testing
    sh "chmod +x gradlew"
    sh "./gradlew clean build"
  }
}