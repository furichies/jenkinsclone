pipeline {
    agent  any;
    stages {
        stage('Calidad de código') {
            steps {
                sh 'echo checking la calidad del código'
            }
        }
        stage('Test Unitario') {
            steps {
                sh 'echo comprobando la aplicación'
            }
        }
        stage('Build') {
            steps {
                sh 'echo creando paquete de aplicación'
            }
        }
   
    stage('Entrega') {
          
          steps {
              sh 'echo realizando la entrega de software'
          }
      }        
      stage('Deploy') {
          
          steps {
              sh 'echo desplegando'
          }
      }
    
	}
}
