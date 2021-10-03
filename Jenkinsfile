def skipRemainingStages = false
pipeline {
    agent any

    stages {
        stage ('compile maven') {
            steps {
               
                    sh 'mvn compile'
                catchError {
            build job: 'system-check-flow'
        }
        echo currentBuild.result
    }
            }
        }
       
        stage ('test maven') {
            steps {
               
                    sh 'mvn test'
                 catchError {
            build job: 'system-check-flow'
        }
        echo currentBuild.result
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
