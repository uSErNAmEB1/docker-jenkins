pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                script {
                    docker.build('static-site')
                }
            }
        }

        stage('Run Container') {
            steps {
                script {
                    sh 'docker rm -f static_site || true'
                   sh 'docker run -d --name static_site -p 9090:80 static-site'
                }
            }
        }
    }
}
