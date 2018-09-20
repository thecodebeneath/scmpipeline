node {
   tools {
      maven 'M3'
   }
   stage('Preparation') {
      git 'https://github.com/jglick/simple-maven-project-with-tests.git'
   }
   stage('Build') {
      sh "mvn -Dmaven.test.failure.ignore clean package"
   }
   stage('Results') {
      junit '**/target/surefire-reports/TEST-*.xml'
      archiveArtifacts 'target/*.jar'
   }
}
