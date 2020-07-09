@Library('Demo-Shared-lib') _

pipeline {

   agent any
   tools {
       maven 'Maven_Home'
   }
  
   stages {

       stage("Code Checkout") {
           steps {
               Checkout(
                   branch_name: "",
                   url_name: ""
               )
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
               build()
               
           }
       }
      stage('SonarStage'){
         sonar()
   }
}
