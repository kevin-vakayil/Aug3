pipeline {
    agent any

    stages {
        stage ('compile maven') {
            
            steps{
                sh 'mvn compil'
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
