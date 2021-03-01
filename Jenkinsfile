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

                    credentialsId: 'jfrog-cred'
                    //username: 'admin',
 				    //password: 'A@runa11''

                )



				rtUpload (
				    serverId: 'ARTIFACTORY_SERVER1',
				    spec: '''{
					  "files": [
					    {
					      "pattern": "**/*.war",
					      "target": "target/"
					    }
					 ]
				    }''',
				    buildName: "${BUILD_DISPLAY_NAME}",
				    buildNumber: "${BUILD_NUMBER}"
				)


            }

        }
        //stage ('sonar') {

          //  steps {


            //        sh '/opt/apps/sonar-scanner-4.6.0.2311-linux/bin/sonar-scanner'

            //}

         //}     
        
        
     
        

    }
}
