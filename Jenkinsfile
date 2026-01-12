pipeline {
  agent any

  stages {
    stage('Check Java') {
  steps {
    bat 'echo JAVA_HOME=%JAVA_HOME%'
    bat 'where javac'
    bat 'javac -version'
  }
}
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

