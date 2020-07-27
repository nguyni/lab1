pipeline {

  environment {
    image = "nguyni/my-nginx_Dev"
    registryCredential = "docker-hub"
    //slackChannelTest = credentials('slack-test')
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
                  dockerImage = docker.build my-nginx_Dev + ":$BUILD_NUMBER"
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


