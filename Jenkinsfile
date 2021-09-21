pipeline{
   agent any
   stages{
      stage("Start Selenium Grid"){    
          steps{
              sh "docker-compose up -d hub chrome firefox"
               }
          }  
      stage("Run Test"){    
          steps{
              sh "docker-compose up login-module search-module"
               }
          }  
      //stage("Bring grid down"){    
        //  steps{
         //     sh "docker-compose down"
           //    }
          //} 
      }
   post{
      always{
         archiveArtifacts artifacts: 'output/**'
         sh "docker-compose down"
      }
      
   }
}
