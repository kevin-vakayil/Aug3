node{
   stage('Mvn Package'){
     sh "mvn clean package"
   }
   stage('Build Docker Image'){
     sh 'docker build -t new .'
   }
   stage('Run Container on Dev Server'){
     def dockerRun = 'docker run -p 8080:8080 -d --name new'
   }
}
