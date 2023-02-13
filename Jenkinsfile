pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        echo 'Building..'
        sh 'mvn compile'
      }
    }

    stage('test') {
      steps {
        echo 'Test'
        sh 'mvn clean test'
      }
    }

    stage('package') {
      steps {
        echo 'Packaging....'
        sh 'mvn package -DskipTests'
        archiveArtifacts(artifacts: '**/target/*.jar', fingerprint: true)
      }
    }

  }
  tools {
    maven 'Maven3.6.3'
  }
}