pipeline {
     agent any
     stages {
         stage('clone my code'){
           git 'http://github/josesachin/maven-project'
           }
         stage('compile my code')
         
             steps {
                 withMaven(maven  :  'LocalMaven')  {
                     sh  'mvn  compile'
                     
                     }
                     }
                     }
                     }
                     }
