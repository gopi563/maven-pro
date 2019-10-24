node {
   
   stage('Code Checkout') { // for display purposes
    git credentialsId: 'githubID', url: 'https://github.com/itrainwarriors/maven-pro.git'  
   }
   stage('Code Build') {
    withMaven(jdk: 'JDK-1.8', maven: 'Maven-3.6.1') {
     sh 'mvn clean compile'
    }  
   }
   stage('Unit Test') {
       withMaven(jdk: 'JDK-1.8', maven: 'Maven-3.6.1') {
        sh 'mvn test'
     }  
   }
   stage('SonarQube Analysis') {
       withMaven(jdk: 'JDK-1.8', maven: 'Maven-3.6.1') {
       sh 'mvn verify sonar:sonar \
          -Dsonar.projectKey=maven-pro-warriors \
          -Dsonar.organization=itrainwarriors \
          -Dsonar.host.url=https://sonarcloud.io \
          -Dsonar.login=2fb178159cb20ad53e509c20446600dc3de796bc '
       }
   } 
   stage('Archive to Jfrog') {
   } 
   stage('Docker Image') {
   } 
   stage('Deploy to Prods') {
   } 
}
