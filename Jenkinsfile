pipeline {
    agent any
  environment {
  DOCKERHUB_CREDENTIALS = credentials('alexroskvas')
  }
    stages {
        
       stage('Build image') {
            steps {
                 sh 'docker build -t alexroskvas/python:latest .'
                 
                
            }
           
       } 
      stage ('Login in Docker Hub'){
        steps{
          sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
        
        
        
        }
      
      }
      
      stage ('Push'){
        steps{
          sh 'docker push alexroskvas/python:latest'
        
        
        }
      }
      
      
      
      
      
      
       stage('Run container') {
            steps {
                 sh "docker run -d --restart=always alexroskvas/python:latest "
                
            }
           
       }  
    }
}
