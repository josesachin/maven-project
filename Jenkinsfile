pipeline {
     agent any
     stages {
         stage('clone my code'){
           git 'https://github.com/josesachin/maven-project/blob/master/Jenkinsfile'
           }
         stage('compile my code')
         
             steps {
                 withMaven(maven  :  'LocalMaven')  {
                     sh  'mvn  clean compile'
                     
                     }
                     }
                     }
                     }
                     }
