def continueBuild = True
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
                      continueBuild = False
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
                      continueBuild = False
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
