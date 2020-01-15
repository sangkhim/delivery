pipeline {
  agent any
    
  stages {    
    stage('Cloning Git') {
      steps {
        git url: 'https://github.com/sangkhim/delivery.git', branch: 'prod', credentialsId: '85a74dfc2fd55104b2c116be8998b36d5a6f2fb0'
      }
    }
    
    stage('Install dependencies') {
      steps {
        sh 'npm install'
      }
    }

    stage('Build SSR') {
      steps {
        sh 'npm run build --prod'
      }
    }
    
    stage('Run on nginx') {
      steps {
         sh 'cp -a www prod'
      }
    }  
  }     
}
