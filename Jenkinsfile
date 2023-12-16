pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                script {
                    sh 'docker build -t nginx:${BUILD_NUMBER} .'
                }
            }
        }
        stage('Run') {
            steps {
                script {
                    sh 'docker run -d --name nginx -p 51001:80 nginx:${BUILD_NUMBER}'
                }
            }
        }

        stage('Remove the container') {
            steps {
                script {
                     sh 'docker rm -f nginx'
                }
            }
        }
        stage('Dockerhub Registry') {
            steps {
                script {
                       sh 'docker tag nginx:${BUILD_NUMBER} piyushdhir121/nginx:a${BUILD_NUMBER}'
                    withCredentials([string(credentialsId: '3535', variable: 'docker creds')]) {
                       sh 'docker push piyushdhir121/nginx:a${BUILD_NUMBER}'
                    }
                }
            }
        }
    }
}
