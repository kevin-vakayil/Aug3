pipeline {
    agent any

    stages {
        stage ('compile maven') {
            steps {
               
                    sh 'mvn compile'
                
            }
        }
        post{
            success {
                }
             failure {
                    script{
                        
                        error "Failed, exiting now..."
                    }
                }
        stage ('test maven') {
            steps {
               
                    sh 'mvn tes'
                
            }
        }
       post{
           success {
                }
             failure {
                    script{
                       
                        error "Failed, exiting now..."
                    }
                }
        stage ('build maven') {
            steps {
               
                    sh 'mvn package'
                
            }
        }
    }
}
