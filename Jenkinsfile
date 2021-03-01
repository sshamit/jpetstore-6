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
					      "target": "tadarepository/"
					    }
					 ]
				    }''',
				    buildName: "${BUILD_ID}",
				    buildNumber: "${BUILD_NUMBER}"
				)


            }

        }
        //stage ('sonar') {

          //  steps {


            //        sh '/opt/apps/sonar-scanner-4.6.0.2311-linux/bin/sonar-scanner'

            //}

         //}     
	    stage ('Deploy'){
		    steps{
		    
		        deploy adapters: [tomcat9(url: 'http://jenkins-server.eastus.cloudapp.azure.com:8081/', 
                              credentialsId: 'c934371c-a087-41cb-b347-cf85bf7e40c8')], 
                     war: '**/*.war',
                     contextPath: 'jpetstore'
		    
		    }
	    
	    }
        
     
        

    }
}
