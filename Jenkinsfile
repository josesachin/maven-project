pipeline {
    agent any


    stages {
        stage('SCM Checkout'){
          git 'https://github.com/josesachin/maven-project'
        }
  }
    {
        stage ('compile Stage') {

            steps {
                withMaven(maven : 'LocalMaven') {
                    sh 'mvn clean compile'
                }
            }
}
}
 {
        stage ('test Stage') {

            steps {
                withMaven(maven : 'LocalMaven') {
                    sh 'mvn clean test'
                }
            }
}
}   
}
