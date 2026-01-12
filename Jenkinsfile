pipeline {
  agent any

  stages {
    stage('Check Java') {
      steps {
        bat 'echo JAVA_HOME=%JAVA_HOME%'
        bat 'dir "%JAVA_HOME%\\bin\\javac.exe"'
        bat '"%JAVA_HOME%\\bin\\java.exe" -version'
        bat '"%JAVA_HOME%\\bin\\javac.exe" -version'
      }
    }

    stage('Build') {
      steps {
        echo 'Building...'
        bat 'if not exist target mkdir target'
        bat '"%JAVA_HOME%\\bin\\javac.exe" -d target ToUpper.java'
      }
    }

    stage('Deploy') {
      steps {
        echo 'Deploying...'
        bat '"%JAVA_HOME%\\bin\\java.exe" -cp target ToUpper "example text"'
      }
    }
  }
}
