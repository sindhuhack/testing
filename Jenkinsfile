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
    email:
    user
    password
     stage ('Deploy-To-Tomcat') {
           steps {
          sshagent(['tomcat']) {
            sh 'scp -o StrictHostKeyChecking=no target/*.war sindhu@172.20.10.2:/home/sindhu/prod/apache-tomcat-8.5.63/webapps/webapp.war'
             }      
          }       
   }
}
}
