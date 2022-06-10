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
                  stage ('Deploying container on remote server') {
                      steps {
                          script {
                           def dockerrun ='docker run -d -p 8091:80 c67ad8c593e9"
                             sshagent(['SSHAGENT']) 
                              {
                                  
                             sh 'ssh -o StrictHostKeyChecking=no ec2-user@172.31.87.200 ${dockerrun}' {
                          }
                      }
                   }      
                }     
             }
          }
       }       
     }  
  }
}
   

