pipeline {

    agent any

     
    stages {
        
        stage ('checkout'){
            steps {
            git  'https://github.com/sshamit/jpetstore-6.git'
            }
        }

        stage ('test') {

            steps {


                   // sh './mvnw test'

            }

         }       

        stage ('package') {

            steps {


                    sh './mvnw clean package'

            }

         }
        stage ('sonar') {

            steps {


                    sh '/opt/apps/devops/sonar-scanner-4.2.0.1873-linux/bin/sonar-scanner'

            }

         }     
        
        
     
        

    }
}
