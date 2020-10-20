pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        echo 'Building...'
        sh 'mvn compile'
      }
    }

    stage('test') {
      steps {
        echo 'Testing....'
        sh 'mvn test'
      }
    }

    stage('package') {
      steps {
        echo 'Packaging..'
        sh 'mvn package -DskipTests'
        archiveArtifacts 'target/*.war'
      }
    }

  }
  tools {
    maven 'Maven'
  }
}