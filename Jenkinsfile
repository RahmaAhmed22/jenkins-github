pipeline {
    agent any

    stages {
        stage('Build and Push Iamge') {
            steps {
                script {
                docker.withRegistry('https://index.docker.io/v1/', 'dockerhub') {
                    def newApp = docker.build "rahmaahmed2002/myapp:${env.BUILD_TAG}"
                    newApp.push()
                }
                }
            }
        }
        stage ('Deploy') {
            steps {
                input 'Do you want to deploy to production?'
                sh "docker compose up -d"
            }
        }
    }
}
