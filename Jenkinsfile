/*
pipleline{
    agent none
    stages{
        stage('Maven Install'){
            agent any
            steps{
                sh 'mvn -f pom.xml clean install'
            }
        }
        stage('Docker Build'){
            agent any
            steps{
                sh 'docker build -t 179653/docker-jenkins-integration .'
            }
        }
        stage('Docker Push'){
            agent any
            steps{
                withDockerRegistry([ credentialsId: "dockerhub", url: ""]){
                    sh 'docker push 179653/docker-jenkins-integration'
                }
            }
        }
    }
}

pipeline {
     agent any
     stages {
          stage("Compile") {
               steps {
                    sh "./mvnw compile"
               }
          }

     }
}
*/
#!groovy
pipeline {
    agent none
   stages {
    stage('Maven Install') {
      agent {
       docker {
         image 'maven:3.5.0'
     }
  }
  steps {
       sh 'mvn clean install'
       }
     }
   }
 }





























