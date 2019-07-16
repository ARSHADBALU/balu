pipeline {
  agent any

    stages{
      stage ('Comple Stage') {

        steps{
            withMaven(maven: 'maven_3_5_0'){
              sh 'mvn clean comple'
            }
          } 
        }
        stage ('Testing Stage') {

          steps{
            withMaven(maven: 'maven_3_5_0'){
              sh 'mvn test'
            }
          } 
        }
        stage ('Deployment Stage') {

        steps{
            withMaven(maven: 'maven_3_5_0'){
              sh 'mvn deploy'
          }
        } 
      }

    }
}