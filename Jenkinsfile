pipeline {
    agent any
    
    stages {
        stage ('Pulling image from ECR') {
            script {
              withDockerRegistry(credentialsId: 'ecr:us-east-1:049742470590', url: 'https://us-east-1.console.aws.amazon.com/ecr/repositories?region=us-east-1') 
              {
                  sh "docker pull 049742470590.dkr.ecr.us-east-1.amazonaws.com/myecrrepo:latest"
                  sh "docker run -d -p 8091:80  c67ad8c593e9 
              }
            }
        }
        
    }
}
