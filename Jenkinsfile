pipeline {
  agent any
  stages {
    stage('Compile') {
      steps {
        sh './mvnw clean compile'
      }
    }

    stage('Static Analysis') {
      steps {
        sh '''mvn clean verify sonar:sonar \\
  -Dsonar.projectKey=Petclinic \\
  -Dsonar.projectName=\'Petclinic\' \\
  -Dsonar.host.url=http://172.31.31.117:9000 \\
  -Dsonar.token=sqp_3086c7ef1becd9ccf441cce9c0de7d970c0f7de0'''
      }
    }

  }
}