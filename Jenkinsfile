pipeline {
    agent { label 'docker' }

    stages {
        stage('Clone Code') {
            steps {
                git 'https://github.com/pujaraamen/autotest1.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t mysite .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker rm -f mysite_container || true'
                sh 'docker run -d -p 8081:80 --name mysite_container mysite'
            }
        }
    }
}
