pipeline {
  agent {
    kubernetes {
      label 'kube-agent'
    }
  }

  environment {
      PROD_KUBE_CONFIG = credentials('prod-kube-config')
  }

  stages {

    stage('test') {
      steps{
        sh "echo 'aaa'"
      }
    }

    stage('Environment setup') {
      steps{
        sh "id"
        sh "pwd"
        sh "apt update"
        sh "apt install curl -y"
        sh "curl -o kubectl https://amazon-eks.s3.us-west-2.amazonaws.com/1.20.4/2021-04-12/bin/linux/amd64/kubectl"
        sh "chmod +x ./kubectl"
        sh "mkdir -p $HOME/bin && cp ./kubectl $HOME/bin/kubectl && export PATH=$PATH:$HOME/bin"
        sh "cp ./kubectl /usr/local/bin/kubectl"
        sh "cp ./kubectl /usr/bin"
        sh "mkdir $HOME/.kube"
        sh "echo $PROD_KUBE_CONFIG | base64 -d > ~/.kube/config"
        sh "whereis kubectl"
        sh "kubectl version"
        sh "kubectl get nodes"
        sh "ls"
      }
    }
  }
}
