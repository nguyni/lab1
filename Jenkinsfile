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
		  sh "docker build -t my-nginx_01 ."
                  sh "docker run -d -p 443:8123 my-nginx_01"
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


