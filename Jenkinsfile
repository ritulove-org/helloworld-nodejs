pipeline {
  agent none
  stages {
    stage('Say Hello') {
     agent { label 'nodejs-app' }
      steps {
        echo 'Hello World! love'   
        sh 'java -version'
      }
    }
  }
}
