node {
   
   stage('Code Checkout') { // for display purposes
    git credentialsId: 'mshakeer011', url: 'https://github.com/itrain-Bharathi/maven-pro.git'  
   }
   stage('Code Build') {
    withMaven(jdk: 'JDK-1.8', maven: 'Maven3.6.1') {
     sh 'mvn clean compile'
    }  
   }
   stage('Unit Test') {
       withMaven(jdk: 'JDK-1.8', maven: 'Maven3.6.1') {
        sh 'mvn test'
     }  
   }
   stage('SonarQube Analysis') {
       withMaven(jdk: 'JDK-1.8', maven: 'Maven3.6.1') {
       sh 'mvn sonar:sonar \
                -Dsonar.projectKey=samplesonartkn \
                -Dsonar.organization=samplesnrpro1 \
                -Dsonar.host.url=https://sonarcloud.io \
                -Dsonar.login=adfe82e15760a73bff75baeec41628361ec7714e '
       }
   } 
   stage('Archive to Jfrog') {
   } 
   stage('Docker Image') {
   } 
   stage('Deploy to Prods') {
   } 
}
