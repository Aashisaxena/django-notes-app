pipeline{
    agent any
    
    stages{
        stage("code clone"){
          steps{
            echo "cloning the code"
            git url: "https://github.com/Aashisaxena/django-notes-app.git", branch:"main"
          }
        }
        
        stage("code build"){
          steps{    
            echo"building the code"
            sh "docker build -t notes-app ."
          }    
        }
        
        stage("code push"){
         steps{
            echo"pushing the code to docker hub"
         }    
        }
        
        stage("code deploy"){
          steps{    
            echo "deploying the code "
            sh "docker-compose down && docker-compose up -d"
          }
        }
        
    }
}
