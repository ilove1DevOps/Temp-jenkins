pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                script {
                    sh 'git clone https://github.com/ilove1DevOps/Temp-jenkins.git'
                }
            }
        }
        stage('Deploy') {
            steps {
                script {
                    echo 'docker build -t nginx .'
                }
            }
        }
    }
}
