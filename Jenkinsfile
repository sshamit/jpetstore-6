pipeline {

    agent any

     
    stages {
        
        stage ('checkout'){
            steps {
            git  'https://github.com/sshamit/jpetstore-6.git'
            }
        }

        

        stage ('package') {

            steps {


                    sh './mvnw clean package'

            }

         }
        
        stage ('deploy') {
            
           
            steps {

              sh 'whoami'  
                
              sh 'cp target/JPetStore.war /home/dineshreddy99077/noida/apache-tomcat-7.0.103/webapps/'

            }
            }
     
        

    }
}
