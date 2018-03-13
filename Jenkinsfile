pipeline {
  agent {
    docker {
      image 'maven:3-alpine'
      args '-v /root/.m2:/root/.m2'
    }
    
  }
  stages {
    stage('Test') {
      parallel {
        stage('Test') {
          steps {
            sh 'mvn test'
          }
          post {
            always {
              junit 'target/surefire-reports/*.xml'
              
            }
            
          }
        }
        stage('Test Too') {
          steps {
            echo 'YOOOOO'
          }
        }
      }
    }
  }
}