pipeline {
    agent any

    stages {
        stage ('compile maven') {
            
            steps{
                script{
                try {
                     sh 'mvn compile'
                     } finally {
                      echo '[FAILURE] Failed to build'
              }
                }
            }
        }
        
        stage ('test maven') {
            steps {
               
                    sh 'mvn test'
                
            }
        }
      
        stage ('build maven') {
            steps {
               
                    sh 'mvn package'
                
            }
        }
    }
}
