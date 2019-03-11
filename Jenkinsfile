pipeline {
    agent any
    stages {
        stage("Run Test") {            
            steps {
                bat "docker-compose up"
            }
        }
        stage("Stop Test") {            
            steps {
                bat "docker-compose down"
            }        
        }
    }
}