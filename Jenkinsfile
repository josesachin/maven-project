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
    {
        stage ('package Stage') {

            steps {
                withMaven(maven : 'LocalMaven') {
                    sh 'mvn clean package'
                }
            }
}
} 
    {
        stage ('verify Stage') {

            steps {
                withMaven(maven : 'LocalMaven') {
                    sh 'mvn clean verify'
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
                withMaven(maven : 'LocalMaven') {
                     sshagent (credentials: ['8f2505ed-76a5-4cd3-a640-3aa97237b036']) {
                     sh 'ssh -o StrictHostKeyChecking=no -l cloudbees 192.168.1.106 ec2-user -a'
                }
            }
}
}
}
