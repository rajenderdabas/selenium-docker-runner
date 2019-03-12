pipeline {
    agent any
    stages {
		stage("Pull Latest Image") {            
            steps {
                bat "docker pull rajenderdabas1/selenium-docker:latest"
            }
        }
        stage("Start Grid") {            
            steps {
                bat "docker-compose up -d hub chrome firefox"
            }
        }
        stage("Run Test") {            
            steps {
                bat "docker-compose up search-module book-flight-module"
            }        
        }
	}
	post{
		always{
			archiveArtifacts artifacts: './**'
			bat "docker-compose down"		
		}
    }
}