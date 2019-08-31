pipeline {
    agent none 
    stages {
        stage('Build') { 
            agent {
                docker {
                    image 'python:3.7.2' 
                }
            }
            steps {
                sh """                
                pip install virtualenv
                virtualenv -p python3 venv
                source venv/bin/activate
                pip install -r requirements.pip
                """
            }
        }
        stage('test') {
          steps {
            sh 'python test_app.py'
          }    
        }
    }
}