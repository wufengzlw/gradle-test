pipeline {
    agent any
    stages {

    stage('Git clone') {
        steps{
          script {
          git branch: "master",
              url: 'https://github.com/wufengzlw/gradle-test',
              credentialsId: 'jenkins-user'
            }
        }
    }

    stage('test') {
      steps{
        sh "echo 'aaa'"
      }
    }
  }
}
