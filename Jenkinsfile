pipeline {
      agent any
  stages {
    stage('CleanWorkspace') {
      steps {
        cleanWs()
      }
    }
    
    stage('Code-Checkout from Git'){  
      steps {
        sh "git clone https://github.com/mhali922/cfn-jenkins-aws.git"
      }
      
    }
    
    stage("List the bucket and Test the connections") {
      steps {
        
