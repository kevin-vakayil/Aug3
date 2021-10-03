pipeline {
    agent any

    stages {
        stage ('compile maven') {
            steps {
               
                 def result = sh returnStatus: true, script:  sh 'mvn compil'
                 if (result != 0) {
                    echo '[FAILURE] Failed to build'
                    currentBuild.result = 'FAILURE'
                    sh "exit ${result}"  
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
