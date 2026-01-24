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
                sh "docker run -d -p 30${env.BUILD_TAG}:80 rahmaahmed2002/myapp:${env.BUILD_TAG}"
            }
        }
    }
}
