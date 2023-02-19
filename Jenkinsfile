pipeline {
  agent any
  stages{
    stage('Build'){
      steps {
        sh 'g++ main/test.cpp -o output'
        build 'PES2UG20CS219-1'
        echo 'Build Success'
      }
    }
    stage('Test') {
      steps {
        sh './output'
        echo 'Testing Success'
      }
    }
    stage('Deploy') {
      when {
        expression {
          currentBuild.result == null || currentBuild.result =='SUCCESS'
        }
      }
      steps {
        echo 'Deployment Success'
      }
    }
  }
  post {
    failure {
      echo 'Pipeline failed'
    }
  }
  
}

    
    
