@Library('Demo-Shared-lib') _

pipeline {

   agent {
       node {
           label 'master'
       }
   }

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

       stage("Compile Code") {
           steps {
               Build(
               sh 'mvn clean install'
           }
       }
   }
}
