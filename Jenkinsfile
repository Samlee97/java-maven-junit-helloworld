@Library('Demo-Shared-lib') _

pipeline {

   agent any
   tools {
       maven 'Maven_Home'
   }
  
   stages {

       stage("Code Checkout") {
           steps {
               script{
               abcd("master", "https://github.com/Samlee97/java-maven-junit-helloworld.git" )
               }
           }
       }

       stage("Build_In_Container") {
          agent {
                docker {
                    image 'samlee18/samlee'
                   reuseNode true
                }
          }
           steps {
               script{
               maven_build()
               
           }
       }
       }
      stage('SonarStage'){
          script{
         sonar_analyse()
   }
      }
}
}
