pipeline {
  agent none
  options { 
    buildDiscarder(logRotator(numToKeepStr: '2'))
    skipDefaultCheckout true
  }
    triggers {
    eventTrigger simpleMatch('hello-api-eli')
  }
  stages {
    stage('Test') {
        agent {
    kubernetes {
      label 'nodejs-app-pod2'
      yamlFile 'nodejs-pod.yaml'
    }
  }
    steps {
        checkout scm
        container('nodejs') {
          echo 'Hello World!'   
          sh 'node --version'
        }
      }
    }
    stage('Build and Push Image') {
      when {
         beforeAgent true
         branch 'master'
      }
      steps {
         echo "TODO - build and push image"
      }
    }
  }
}
