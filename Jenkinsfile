def continueBuild = true
pipeline {
    agent any

    stages {
        stage ('compile maven') {
            
            steps{
            script{
                try {
                     sh 'mvn compile'
                     } catch(Exception e) {
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
                      sh 'mvn tes'
                     } finally {
                      echo '[FAILURE] Failed to build' 
                      currentBuild.result = 'FAILURE'
                      throw(error)
                      
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
