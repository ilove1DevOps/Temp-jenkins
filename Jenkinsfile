pipeline {
    agent any
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
