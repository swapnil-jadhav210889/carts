pipeline {
    agent any

    tools {
      maven 'Maven3.6.3'   
    }

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
                sh 'mvn -DskipTests package'
                archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true
            }
        }
    }
}
