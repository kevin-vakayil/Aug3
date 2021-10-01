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
            when { skipRemainingStages == false {  !skipRemainingStages } }
            steps {
               
                    sh 'mvn test'
                 script {
                    skipRemainingStages = true

                    println "skipRemainingStages = ${skipRemainingStages}"
                }
                
            }
        }
      
        stage ('build maven') {
            when { skipRemainingStages == false {  !skipRemainingStages } }
            steps {
               
                    sh 'mvn package'
                
            }
        }
    }
}
