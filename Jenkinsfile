pipeline {

  environment {
    image = "nguyni/my-nginx_Dev"
    registryCredential = "docker-hub"
    slackChannelTest = credentials('Nhuan#2020GH')
    dockerImage = ''
  }

  agent any

  stages {

            stage('Cloning Git') {
              steps {
                git 'https://github.com/nguyni/lab1.git'
              }
            }
	    stage('Build Image') {
	      steps{
	        script {
	          //sh "docker build -t my-nginx_01 ."
                  dockerimage = docker.build image + ":$BUILD_NUMBER"
	        }
	      }
	    }
	    stage('Deploy Test Server') {
	      steps{
	        script {
	          sh "./deploy-test.sh ${env.BUILD_ID} ${env.image}:${env.BUILD_ID}"
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


