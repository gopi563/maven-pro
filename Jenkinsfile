node {
   
   stage('Code Checkout') { // for display purposes
    git credentialsId: 'gopi563', url: 'https://github.com/gopi563/maven-pro.git'  
   }
   stage('Code Build') {
    withMaven(jdk: 'jdk1.8', maven: 'maven3.6.1') {
     sh 'mvn clean compile'
    }  
   }
   stage('Unit Test') {
       withMaven(jdk: 'jdk1.8', maven: 'maven3.6.1') {
        sh 'mvn test'
     }  
   }
   stage('SonarQube Analysis') {
       withMaven(jdk: 'jdk1.8', maven: 'maven3.6.1') {
       sh 'mvn sonar:sonar \
             -Dsonar.projectKey=sonarproject112 \
             -Dsonar.organization=sponarproject \
             -Dsonar.host.url=https://sonarcloud.io \
             -Dsonar.login=f530d2f10fe89a53ffc6003965a26a6f5845fd0c'
       }
   } 
   stage('Archive to Jfrog') {
   } 
   stage('Docker Image') {
   } 
   stage('Deploy to Prods') {
   } 
}
