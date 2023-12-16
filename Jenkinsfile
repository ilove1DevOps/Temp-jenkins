pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                script {
                    sh 'docker build -t nginx .'
                }
            }
        }
        stage('Run') {
            steps {
                script {
                    sh 'docker run -d --name nginx -p 51001:80 nginx:latest'
                }
            }
        }

        stage('Remove the container') {
            steps {
                script {
                    {
                        sh 'docker rm -f nginx'
                    }
                }
            }
        }
        stage('Dockerhub Registry') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'Docker-creds-01', url: 'https://hub.docker.com/') {
                        sh 'docker push nginx:latest'
                    }
                }
            }
        }
    }
}
