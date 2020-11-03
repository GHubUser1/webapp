pipeline {
    agent any
    stages {
        stage ('Checkout') {
          steps {
            git 'https://github.com/GHubUser1/webapp'
          }
        }

        stage('Build') {
            steps {
                bat 'mvn clean package'
                //junit '**/target/surefire-reports/TEST-*.xml'
                //archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
            }
			//post {
                //success {
                  //  echo 'Now Archiving To Nexus...'
                   // archiveArtifacts artifacts: '**/target/*.war'
               // }
            //}
        }
        stage('Deploy') {
            steps {
                //input 'Do you approve the deployment?'
                // copy the application
                //sh 'scp target/*.war jenkins@192.168.50.10:/opt/pet/'
                bat 'copy target/*.war C:/Program Files/Apache Software Foundation/Tomcat 9.0/webapps'
            }
        }
	
    }
}
