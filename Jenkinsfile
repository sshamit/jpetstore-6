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

                
              sh './mvnw cargo:run -P tomcat70'
               

            }
            }
     
        

    }
}
