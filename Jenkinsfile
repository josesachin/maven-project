pipeline {
    agent any


    stages {
        stage('SCM Checkout'){
          git 'https://github.com/josesachin/maven-project'
        }
  }  
{
        stage ('compile Stage') {
            agent {label 'maven' }
            steps {
                withMaven(maven : 'LocalMaven') {
                    sh 'mvn clean compile'
                }
            }
}
}
{
        stage ('install Stage') {

            steps {
                withMaven(maven : 'LocalMaven') {
                    sh 'mvn clean install'
                }
            }
}
}
     {
        stage ('deploy Stage') {

            steps {
                     sshagent (credentials: ['8f2505ed-76a5-4cd3-a640-3aa97237b036']) {
                     sh 'scp -o StrictHostKeyChecking=no */target/*.war ec2-user@13.235.78.99:/usr/share/tomcat/webapps'
                }
            }
}
}
}
