pipeline {
    agent any

    stages {
       
        stage ('Deploy') {
            steps {
                //input 'Do you want to deploy to production?'
                sh "docker compose up -d"
            }
        }
    }
}
