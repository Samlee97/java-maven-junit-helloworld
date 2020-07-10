@Library('Demo-Shared-lib') _

pipeline {

   agent any
   tools {
       maven 'Maven_Home'
   }
  
   stages {

       stage("Code Checkout") {
           steps {
               
               gitCheckout("master", "https://github.com/Samlee97/java-maven-junit-helloworld.git" )
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
               
               maven_build()
               
           }
       
       }
      stage('SonarStage'){
         steps{
         
        
         sonar_analyse()
   }
      
      }
      stage('QualityGate'){
         steps{
            sonar_quality_gate()
         }
      }
}
}
