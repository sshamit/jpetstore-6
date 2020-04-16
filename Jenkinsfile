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
//        stage ('sonar') {

//            steps {


  //                  sh 'sonar-scanner'

  //          }

  //       }     
        
        stage ('deploy') {
            
           
            steps {

              //sh 'rm -rf /home/dineshreddy99077/noida/apache-tomcat-7.0.103/webapps/JPetStore'
              //sh 'rm -f /home/dineshreddy99077/noida/apache-tomcat-7.0.103/webapps/JPetStore.war' 
                
              sh 'cp target/JPetStore.war /home/dineshreddy99077/noida/apache-tomcat-7.0.103/webapps/'

            }
            }
     
        

    }
}
