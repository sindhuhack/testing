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
          sshagent(['tomcat-cred']) {
            sh 'scp -o StrictHostKeyChecking=no target/*.war ubuntu@54.162.35.243:/home/ubuntu/prod/apache-tomcat-8.5.63/webapps/webapp.war'
             }      
          }       
   }
}
}
