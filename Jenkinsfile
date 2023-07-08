pipeline {
  agent any
  stages {
    stage('compile') {
      steps {
        sh './mvnw clean compile'
      }
    }

    stage('static analysis') {
      steps {
        sh '''mvn clean verify sonar:sonar \\
  -Dsonar.projectKey=petclinic \\
  -Dsonar.projectName=\'petclinic\' \\
  -Dsonar.host.url=http://13.235.215.239:9000 \\
  -Dsonar.token=sqp_1120c6cc208cc397900195b858501caae1dbfccb'''
      }
    }

    stage('Static Analysis') {
      steps {
        sh '''./mvn clean verify sonar:sonar \\
  -Dsonar.projectKey=Petclinic \\
  -Dsonar.projectName=\'Petclinic\' \\
  -Dsonar.host.url=http://13.235.215.239:9000 \\
  -Dsonar.token=sqp_89cbcb1e2b503898d2ac1a9bd49383f0f641b788'''
      }
    }

    stage('Unit test') {
      steps {
        sh './mvnw "-Dtest=**/Petclinic/*/*.java" test'
      }
    }

  }
}