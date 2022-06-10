pipeline {
    agent any
    
    stages {
        stage ('Pulling image from ECR') {
           steps { 
        
              script {
                  docker.withRegistry("https://049742470590.dkr.ecr.us-east-1.amazonaws.com/myecrrepo:latest" , "ecr:us-east-1:AWS") 
              {
                 sh "docker pull 049742470590.dkr.ecr.us-east-1.amazonaws.com/myecrrepo:latest"
                 sh "docker run -d -p 8089:80  c67ad8c593e9"
              }
              
            }
          }  
        
        }
  }

}
