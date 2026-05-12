pipeline { 
 agent any 
 environment {
        // Appends Docker to the runtime path for this execution only
        PATH = "C:\\Program Files\\Docker\\Docker\\resources\\bin;${env.PATH}"
    }
 stages { 
 
  stage('Clone') { 
   steps { 
    git branch:"main",
    url:'https://github.com/AkashB29/ci-node-app.git' 
   } 
  } 
 
    stage('Build Docker Image') { 
   steps { 
    bat 'docker build -t web-app .' 
   } 
  } 
 
  stage('Run Docker Container') { 
   steps { 
    bat 'docker run -d -p 8081:81 --name web-container web-app' 
   } 
  } 
 
 } 
 
} 