pipeline {

  environment {
    image = "nguyni/my-nginx_dev"
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
                  dockerImage = docker.build image + ":$BUILD_NUMBER"
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
	           docker.withRegistry( 'Nhuan#2020DH', registryCredential ) {
		   dockerImage.push() 
	        }
	      }
		}     
	}
  }
}


