pipeline {
    agent  any;
    stages {
        stage('Preparando el entorno') {
            steps {
                sh 'python -m pip install -r requirements.txt'
            }
        }
        stage('Calidad de código') {
            steps {
                sh 'python -m pylint app.py'
            }
        }
        stage('Tests') {
            steps {
                sh 'python -m pytest'
            }
        }
   
    stage('Build') {
          steps {
              sh 'exit 1'
          }
      }        
      stage('Delivery') {
          steps {
              sh 'exit 1'
          }
      }
    stage('Deploy') {
	steps {
	   sh ' exit 1'
	}
    }
    }

}

