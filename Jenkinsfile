node {
   
   stage('Code Checkout') { // for display purposes
    git credentialsId: 'anshu8755993241', url: 'https://github.com/itrainwarriors/maven-pro.git'  
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
       sh 'mvn verify sonar:sonar \
          -Dsonar.projectKey=mavenexample-warrior \
          -Dsonar.organization=anshu \
          -Dsonar.host.url=https://sonarcloud.io \
          -Dsonar.login=ef0327fddb530329a89e39f72ae8c060eb96ce47  '
       }
   } 
   stage('Archive to Jfrog') {
   } 
   stage('Docker Image') {
   } 
   stage('Deploy to Prods') {
   } 
}
