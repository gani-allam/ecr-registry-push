pipeline {
  agent any
  stages {
    stage('Git CheckOut') {
      steps {
        git(branch: 'main', url: 'https://github.com/iomegak12/scbv4-casestudy')
      }
    }

    stage('moving to the caliculation folder') {
       steps {
          sh 'ls -l'
          sh 'cd source/ calculation-offer-service'
          sh 'ls -l'
        }
    }
  }
}
