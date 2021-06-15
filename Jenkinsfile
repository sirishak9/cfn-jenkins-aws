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
        git credentialsId: 'GIT_CREDENTIALS', url: 'https://github.com/mhali922/cfn-jenkins-aws.git'
        //sh "git clone https://github.com/mhali922/cfn-jenkins-aws.git"
      }
      
    
    }
    stage("List the bucket and Test the connections") {
      steps {
      withCredentials([[$class: 'AmazonWebServicesCredentialsBinding', accessKeyVariable: 'AWS_ACCESS_KEY_ID', credentialsId: 'aws-user', secretKeyVariable: 'AWS_SECRET_ACCESS_KEY']])
                              {
                                    sh "aws s3 ls"
                              }
                               }
    }
     stage("Run cfn") {                      
           steps {
           withCredentials([[$class: 'AmazonWebServicesCredentialsBinding', accessKeyVariable: 'AWS_ACCESS_KEY_ID', credentialsId: 'aws-user', secretKeyVariable: 'AWS_SECRET_ACCESS_KEY']])
                             {
                                   sh "cd $workspace && aws cloudformation create-stack --region us-east-1 --stack-name S3-bucket --template-body file://s3.yml"
                             }
                             }
                             }
                             }
                             }
                 
        
