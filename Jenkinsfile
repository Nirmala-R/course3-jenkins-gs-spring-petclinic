pipeline {
    agent any
    
    stages {    
        stage("checkout"){
            steps {
               git branch: 'main', url: 'https://github.com/Nirmala-R/course3-jenkins-gs-spring-petclinic'
            }
     }
        stage("build"){
            steps {
                sh "mvn package"
            }
     }

        stage("capture"){
            steps {
               archiveArtifacts '**/target/*.jar'
               jacoco()
               junit '**/target/surefire-reports/TEST*.xml'
            }
      }
     }
   }
