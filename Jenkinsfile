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

              sh 'who am i'  
              //sh './mvnw cargo:run -P tomcat70'
              //sh '''
              
              //deploy adapters: [tomcat7(credentialsId: 'TomcatCred', path: '', url: 'http://34.67.246.242:7070/')], contextPath: '/jpetstore', war: 'target/JPetStore.war'
              
              //'''
                
              sh 'cp target/JPetStore.war /home/dineshreddy99077/noida/apache-tomcat-7.0.103/webapps/'

            }
            }
     
        

    }
}
