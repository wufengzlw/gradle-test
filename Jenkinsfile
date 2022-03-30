pipeline {
  agent {
    kubernetes {
      label 'kube-agent'  // all your pods will be named with this prefix, followed by a unique id
    }
  }
    stages {
    stage('test') {
      steps{
        sh "echo 'aaa'"
      }
    }
  }
}
