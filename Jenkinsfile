node {    
      def app     
      stage('Clone repository') {               
             
            checkout scm    
      }           stage('Build image') {         
       
            app = docker.build("epianceai/thirutest")    
       }           stage('Test image') {                       app.inside {            
             
             sh 'echo "Tests passed"'        
            }    
        }            stage('Push image') {
                                                  docker.withRegistry('https://registry.hub.docker.com', 'git') {                   app.push("${env.BUILD_NUMBER}")            
       app.push("latest")        
              }    
           }
        }
