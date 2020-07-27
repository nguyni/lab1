pipeline {

  agent any

  stages {

            stage('Cloning Git') {
              steps {
                git 'https://github.com/nguyni/lab1.git'
              }
            }
            stage('Building image') {
              steps{
                script {
                  sh "ls -l"
		  sh "docker build -t my-nginx ."
                  sh "docker run -d -p 443:80 my-nginx"
                }
              }
            }
            stage('Testing image') {
              steps{
                script {
                  sh "echo 3333"
                }
              }
            }
                stage('Pushing Image') {
              steps{
                script {
                  sh "echo 5555"
                }
              }
                }
        }
}


