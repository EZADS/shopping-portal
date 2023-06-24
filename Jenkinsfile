pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'this is the build job'
        sh 'npm install'
        sleep 4
      }
    }

    stage('Test') {
      steps {
        echo 'this is the test job'
        sh 'npm test'
      }
    }

    stage('Package') {
      steps {
        echo 'this is the package job'
        sh 'npm run package'
      }
    }

    stage('Archive') {
      steps {
        archiveArtifacts '**/distribution/*.zip'
      }
    }

  }
  tools {
    nodejs 'nodejs'
  }
  post {
    always {
      echo 'this pipeline has completed...'
    }

  }
}