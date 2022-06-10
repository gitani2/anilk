pipeline {
    agent any
    
    stages {
        stage ('Pulling image from ECR') {
           steps { 
        
              script {
                  docker.withRegistry("https://049742470590.dkr.ecr.us-east-1.amazonaws.com/myecrrepo:latest" , "ecr:us-east-1:AWS") 
              {
                 sh "docker pull 049742470590.dkr.ecr.us-east-1.amazonaws.com/myecrrepo:latest"
                  
              }
           }
         }    
       }
                  stage ('Deploying container on remote server') {
                      steps {
                          script {
                           def dockerRun ='docker run -d -p 8091:80 049742470590.dkr.ecr.us-east-1.amazonaws.com/myecrrepo:latest'
                              sshagent(['UBUNTU']) {
                              sh "ssh -o StrictHostKeyChecking=no ubuntu@172.31.87.200 ${dockerRun}"
                          }
                      }
                   }      
                }     
             }
          }
              

   

