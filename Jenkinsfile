pipeline {
    agent any
    stage('Build') 
                {
                steps {
      	          sh 'git clone https://github.com/ilove1DevOps/Temp-jenkins.git'
                  }
            
        }
    stage('Deploy') {
                     steps {
                echo 'docker build -t nginx .'
            }
        }
}
