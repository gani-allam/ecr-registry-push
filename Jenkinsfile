pipeline {
  agent any
  stages {
    stage('Git CheckOut') {
      steps {
        git(branch: 'main', url: 'https://github.com/iomegak12/scbv4-casestudy')
      }
    }

    stage('moving to the caliculation folder') {
      parallel {
        stage('moving to the caliculation folder') {
          steps {
            sh 'cd scbv4-casestudy/scbv4-casestudy/source/ calculation-offer-service'
            sh 'ls -l'
          }
        }

        stage('getting folder structure') {
          steps {
            sh 'ls -l'
          }
        }

      }
    }

  }
}