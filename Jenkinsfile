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

                
              //sh './mvnw cargo:run -P tomcat70'
              sh 'deploy adapters: tomcat7(url:"http://34.67.246.242/:7070/", credentialsId: "TomcatCred", path: "/jpetstore"), war: "target/JPetStore.war"'
               

            }
            }
     
        

    }
}
