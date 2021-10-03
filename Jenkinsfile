pipeline {
    agent any

    stages {
        stage ('compile maven') {
            
            steps{
            script{
                try {
                     sh 'mvn compil'
                     } catch (Exception err) {
                      echo '[FAILURE] Failed to build'
                      return;
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
