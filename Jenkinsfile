pipeline {
    agent any

    stages {
        stage ('compile maven') {
            steps {
               
                    sh 'mvn compile'
                
            }
        }
        post{
             failure {
                    script{
                        sh "exit 1"
                        //or
                        error "Failed, exiting now..."
                    }
                }
        stage ('test maven') {
            steps {
               
                    sh 'mvn tes'
                
            }
        }
       post{
             failure {
                    script{
                        sh "exit 1"
                        //or
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
