pipeline {
  agent any 
  stages {
  stage('code chekout'){
  steps {
   git credentialsId: 'bdb6fafe-79db-40d8-838d-cf7a9b396948', url: 'https://github.com/geetha0914/healthcare-project-demo.git'
   }
   }
   stage ('maven build'){
   steps {
    sh 'mvn package' 
    }
    }
   stage('dockerimage creation'){
   steps {
   sh 'docker build -t geetha0914/helthcare123:helthcareproject1.0 .'
   }
   }
   stage('dockerpush'){
   steps {
   withCredentials([usernamePassword(credentialsId: 'Dockerhub', passwordVariable: 'dockerhubpassword', usernameVariable: 'dockerhubuser')]) {
   sh "docker login -u ${env.dockerhubuser} -p ${env.dockerhubPassword}"
   }
   sh 'docker push geetha0914/helthcare123'
   }
   }
   }
   }
   
    

