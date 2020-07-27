pipeline {

  agent any

  stages {

            stage('Cloning Git') {
              steps {
                git 'https://github.com/schogini/HOOK-TEST-P02-GITHUB.git'
              }
            }
            stage('Building image') {
              steps{
                script {
                  sh "ls -l"
                  sh "docker build -t my-nginx"
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
	    stage('Cloning Git') {
	      steps {
	        git 'https://github.com/schogini/HOOK-TEST-P02-GITHUB.git'
	      }
	    }
	    stage('Building image') {
	      steps{
	        script {
	          sh "ls -l"
	          sh "echo 2222"
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
	          sh "echo 9999999"
	        }
	      }
		}     
	}
}

