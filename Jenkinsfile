def continueBuild = True
pipeline {
    agent any

    stages {
        stage ('compile maven') {
            
            steps{
            script{
                try {
                     sh 'mvn compil'
                     } finally {
                      echo '[FAILURE] Failed to build'
                      continueBuild = False
              }
                }            
        }
        }
        
        stage ('test maven') {
             script{
            if (!continueBuild) {
                 currentBuild.result = 'ABORTED'
                  error('Stopping early…')
                                }
                    }  
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
