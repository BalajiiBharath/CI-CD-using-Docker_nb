pipeline {
    agent any
  
    stages{
        stage('SCM Checkout'){
          steps{
             git credentialsId: 'git', url: 'https://github.com/BalajiiBharath/CI-CD-using-Docker_nb.git'
           }
        }
   stage('Execute Maven') {
           steps {
             
                sh 'mvn package'             
          }
        }
        stage('Docker Build and Tag') {
           steps {
              
                sh 'docker build -t samplewebapp:latest .' 
                sh 'docker tag samplewebapp navyaa14/samplewebapp:latest'
                //sh 'docker tag samplewebapp nikhilnidhi/samplewebapp:$BUILD_NUMBER'
               
          }
        }

    }
}
