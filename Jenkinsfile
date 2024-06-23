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
    // stage('Clone') {
    //   steps {
    //     script {
    //       echo "Starting the Clonning..."
    //       // Create a file within the Jenkins workspace
    //         checkout([$class: 'GitSCM', 
    //                 branches: [[name: 'main']], 
    //                 userRemoteConfigs: [[url: 'https://github.com/mansuralamkhan/java-project.git']]
    //                 ])
    //       echo "Completed the Hello stage."
    //     }
    //   }
    // }

    

    stage('Build'){
        steps{
         sh 'mv clean deploy'
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
