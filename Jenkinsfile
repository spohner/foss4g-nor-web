pipeline {
  agent any
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
      steps {
        emailext(subject: 'Oppdatert foss4g-nor-web / spohner', attachLog: true, from: 'no-reply@tardis.no', to: 'steffen@pohnerhenriksen.com', body: 'Oppdatert!')
      }
    }
  }
}