pipeline {
   tools {
      maven 'M3'
   }
   stages {
      stage('Preparation') {
         steps {
            git 'https://github.com/jglick/simple-maven-project-with-tests.git'
         }
      }
      stage('Build') {
         steps {
            sh "mvn -Dmaven.test.failure.ignore clean package"
         }
      }
      stage('Results') {
         steps {
            junit '**/target/surefire-reports/TEST-*.xml'
            archiveArtifacts 'target/*.jar'
         }
      }
   }
}
