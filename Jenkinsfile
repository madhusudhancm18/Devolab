pipeline{
  agent any
  stages {
    stage('Checkout'){
      steps{
        Checkout scm
      }
    }
    stage('Bulid'){
      steps{
        echo 'Checking Python application'
        bat'python -m py_compile app.py'
      }
    }
    stage('Test'){
      steps{
        echo 'Executing automated tests'
        bat 'python -m unittest app'
      }
    }
    stage('Run Application'){
      steps{
        bat 'python app.py'
      }
    }
  }
  
    post {
      success{
        echo 'CI Pipeline completed succesfully'}
      failure{
        echo 'CI pipeline failed'
      }
    }
}
        
