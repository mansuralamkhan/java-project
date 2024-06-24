pipeline {
  agent {
      node{
           label 'maven'
      }
   
  }

//   environment{
//     PATH = "/opt/apche-maven-3.9.8/bin:$PATH"
//   }

  stages {
    

    stage('Build'){
      
        steps{
         sh '/opt/maven/bin/mvn clean deploy'
        }
    }
  

  stage('SonarQube analysis'){
    tools{
      jdk 'java17'
    }
    environment {
    
      scannerHome = tool 'java-sonar-scanner'
       }
       steps{
        withSonarQubeEnv('sonar-server'){
          sh "${scannerHome}/bin/sonar-scanner"
        }
       }
  }
  }

  post {
    always {
      echo "Pipeline execution completed."
      script {
        sh 'ls -la $WORKSPACE'
      }
    }
  }
}
