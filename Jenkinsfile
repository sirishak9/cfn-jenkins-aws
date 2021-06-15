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
      withCredentials([[$class: 'AmazonWebServicesCredentialsBinding', accessKeyVariable: 'AWS_ACCESS_KEY_ID', credentialsId: 'aws-user', secretKeyVariable: 'AWS_SECRET_ACCESS_KEY'
                              {
                                    sh "aws S3 ls"
                              }
                              }
                              }
     stage("Run cfn") {                      
           steps {
           withCredentials([[$class: 'AmazonWebServicesCredentialsBinding', accessKeyVariable: 'AWS_ACCESS_KEY_ID', credentialsId: 'aws-user', secretKeyVariable: 'AWS_SECRET_ACCESS_KEY'
                             {
                                   sh "cd $workspace/cfn-task && aws cloudformation create-stack --region us-east-1 --stack-name S3-bucket --template-body file://s3.yml"
                             }
                             }
                             }
                             }
                             
                             }
                 
        
