pipeline {
    agent any

    stages {
       
        stage ('build images') {
            steps {
                //input 'Do you want to deploy to production?'
                sh "docker compose up -d"
            }
        }
    }
}
