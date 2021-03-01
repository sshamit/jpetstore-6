pipeline {

    agent any

     
    stages {
        
        stage ('checkout'){
            steps {
            git  'https://github.com/Dharani61/jpetstore-6.git'
            }
        }

        stage ('test') {

            steps {

                    sh 'echo "hello"'
                   // sh './mvnw test'

            }

         }       

        stage ('package') {

            steps {


                    sh './mvnw clean package'

            }

         }
        stage ('Artifactory configuration') {

            steps {

                rtServer (

                    id: "ARTIFACTORY_SERVER1",

                    url: "https://tadadharani.jfrog.io/artifactory",

                //    credentialsId: 'jfrog'
                   username: 'tada.dharani@hcl.com',
 				   password: 'Monday$12345'

                )
                
                rtUpload (
                    serverId: 'ARTIFACTORY_SERVER1',
                    specPath: 'target/jpetstore.war',
                    failNoOp: true,

                    // Optional - Associate the uploaded files with the following custom build name and build number.
                    // If not set, the files will be associated with the default build name and build number (i.e the
                    // the Jenkins job name and number).
                    buildName: 'jpetstore',
                    buildNumber: '2.0.21'
                )

            }

        }
        stage ('sonar') {

            steps {


                    sh '/opt/apps/sonar-scanner-4.6.0.2311-linux/bin/sonar-scanner'

            }

         }     
        
        
     
        

    }
}
