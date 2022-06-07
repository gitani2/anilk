pipeline {
    agent any
    
    stages {
        stage ('Pulling image from ECR') {
            script {
              withDockerRegistry(credentialsId: 'ecr:us-east-1:049742470590', url: '049742470590.dkr.ecr.us-east-1.amazonaws.com/myecrrepo')
              {
                  sh "docker pull 049742470590.dkr.ecr.us-east-1.amazonaws.com/myecrrepo"
                  sh "docker run -d -p 8091:80  c67ad8c593e9 
              }
            }
        }
        
    }
}
