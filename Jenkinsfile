pipeline {
  agent any

  stages {
    stage('Build') {
      steps {
        echo 'Building...'
        bat 'if not exist target mkdir target'
        bat 'javac -d target ToUpper.java'
      }
    }

    stage('Deploy') {
      steps {
        echo 'Deploying...'
        bat 'java -cp target ToUpper "example text"'
      }
    }
  }
}
