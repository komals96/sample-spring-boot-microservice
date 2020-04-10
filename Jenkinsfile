// Scripted Pipeline with stages
pipeline {
  agent { label 'master' }
  stages {
    stage('Source') { // Get code
      //steps {
      //  // get code from our Git repository
      //  git 'https://github.com/vinayaka-rs/sample-spring-boot-microservice.git'
      //}
      steps {
        scm {
          git {
            remote {
              url("https://github.com/vinayaka-rs/sample-spring-boot-microservice.git")
              credentials("github_id")
            }
            extensions {
              wipeOutWorkspace()
            }
            branch("master")
          }
        }
      }
    }
    stage('Compile') { // Compile and do unit testing
      steps {
        // run Gradle to execute compile and unit testing
        //sh "./gradlew clean build"
        gradle {
          fromRootBuildScriptDir(true)
          makeExecutable(true)
          tasks('clean build')
        }
      }
    }
  }
}