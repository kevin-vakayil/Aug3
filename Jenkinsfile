def skipRemainingStages = false
pipeline {
    agent any

    stages {
        stage ('compile maven') {
            steps {
               
                    sh 'mvn compile'
                 script {
                    skipRemainingStages = true

                    println "skipRemainingStages = ${skipRemainingStages}"
                }
            }
        }
       
        stage ('test maven') {
            if (skipRemainingStages == false) {
                 
                    !skipRemainingStages
                
            }
            steps {
               
                    sh 'mvn test'
                
            }
        }
      
        stage ('build maven') {
            if (skipRemainingStages == false)  {
                
                    !skipRemainingStages
                
            }
            steps {
               
                    sh 'mvn package'
                
            }
        }
    }
}
