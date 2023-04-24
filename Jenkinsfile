pipeline {
    agent  {user 'jenkins'}
    stages {
        stage('Extracción de información'){
            steps {
                sh 'whoami'
                sh 'echo $PATH'
                sh 'export PATH=$PATH:/var/jenkins_home/.local/bin/'
                sh 'echo $PATH'
            }
        }
        stage('Preparamos el entorno') {
            steps {
                sh 'python3 -m pip install -r requirements.txt'
            }
        }
        stage('Calidad de código') {
            steps {
                sh 'python3 -m pylint app.py'
            }
        }
        stage('Tests unitarios') {
            steps {
                sh 'python3 -m pytest'
            }
        }
   
    stage('Build - creando artefacto (imagen docker en este caso)') {
          agent { 
            node{
              label "DockerServer"; 
              }
          }
          steps {
              sh 'docker build https://github.com/richiinstructor/jenkins.git#main -t richijenkins:latest'
          }
      }        
      stage('Despliegue') {
          agent { 
            node{
              label "DockerServer"; 
              }
          }
          steps {
              sh 'docker run -tdi -p 5000:5000 richijenkins:latest'
          }
      }
    }

}

