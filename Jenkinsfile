pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
               script {
                    git branch: 'main',
                        url: 'https://github.com/ilove1DevOps/Temp-jenkins.git'
                }
            }
        }
    stage('Build') {
            steps {
                steps {
      	          sh 'docker build -t nginxwebsite .'
                  }
            }
        }
        stage('Deploy') {
            steps {
                echo 'docker run -d nginxwebsite:latest -p 51001:80'
            }
        }
    }
}
