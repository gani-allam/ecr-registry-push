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
          sh 'cd source/calculation-offer-service/'
          sh 'ls -l'
        }
    }
    
    stage('aws login') {
      sh 'aws ecr get-login-password --region ap-south-1 | docker login --username AWS --password-stdin 142198642907.dkr.ecr.ap-south-1.amazonaws.com'
    }
    
    stage('Building image'){
     sh 'docker build -t ganesh-jenkins-calculation-service .' 
    }
    
    stage('Tagging image'){
      sh 'docker tag ganesh-jenkins-calculation-service:latest 142198642907.dkr.ecr.ap-south-1.amazonaws.com/ganesh-jenkins-calculation-service:latest'
    }
    
    stage('Pushing Image'){
      sh 'docker push 142198642907.dkr.ecr.ap-south-1.amazonaws.com/ganesh-jenkins-calculation-service:latest'
    }
  }
}
