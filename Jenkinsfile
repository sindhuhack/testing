pipeline {
  agent any 
  tools {
    maven 'maven'
  }
  stages {
    stage ('Build') {
      steps {
      sh 'mvn clean package'
       }
    }
    
    stage ('Deploy-To-Tomcat') {
           steps {
          sshagent(['JRNTR']) {
               sh 'scp -o StrictHostKeyChecking=no target/*.war ec2-user@54.226.250.24:/opt/apache-tomcat-8.5.56/webapps/webapp.war'
             }      
          }       
   }
}
}
