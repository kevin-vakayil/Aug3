def continueBuild = true
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
                      continueBuild = false
                      currentBuild.result = 'ABORTED'
                      error('Stopping early…')
              }
                }            
        }
        }
        
        stage ('test maven') {
            steps {
             script{
            if (!continueBuild) {
                 currentBuild.result = 'ABORTED'
                  error('Stopping early…')
                                }
                 
                 try {
                      sh 'mvn test'
                     } finally {
                      echo '[FAILURE] Failed to build'
                      continueBuild = false
              }
                
                    }  
   
                
            }
        }
      
        stage ('build maven') {
            steps {
               
                    sh 'mvn package'
                
            }
        }
    }
}
