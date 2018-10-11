pipeline {
  agent {
    docker {
      image 'node:6-alpine'
      args '-p 3000:3000'
    }

  }
  stages {
    stage('NPM INSTALL') {
      agent any
      steps {
        sh 'npm install'
      }
    }
    stage('DEPLOY') {
      agent any
      steps {
        sh 'npm run deploy'
      }
    }
    stage('email') {
      agent any
      steps {
        emailext(subject: 'Oppdatert foss4g-nor-web / spohner', attachLog: true, from: 'no-reply@tardis.no', to: 'steffen@pohnerhenriksen.com', body: 'Oppdatert!')
      }
    }
  }
}