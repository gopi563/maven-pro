node {
   
   stage('Code Checkout') { // for display purposes
    git credentialsId: 'mshakeer011', url: 'https://github.com/itrain-Bharathi/maven-pro.git'  
   }
   stage('Code Build') {
    withMaven(jdk: 'jdk', maven: 'maven') {
     sh 'mvn clean compile'
    }  
   }
   stage('Unit Test') {
       withMaven(jdk: 'jdk', maven: 'maven') {
        sh 'mvn test'
     }  
   }
   stage('SonarQube Analysis') {
       withMaven(jdk: 'jdk', maven: 'maven') {
       sh mvn verify sonar:sonar \
            -Dsonar.projectKey=Maven-pro-example \
            -Dsonar.organization=itrainpulsars \
            -Dsonar.host.url=https://sonarcloud.io \
            -Dsonar.login=c6769f157980296bb9ea4decb5097b55fb9cd23f
       }
   } 
   stage('Archive to Jfrog') {
   } 
   stage('Docker Image') {
   } 
   stage('Deploy to Prods') {
   } 
}
