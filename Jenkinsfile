pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
              dir("Spring") {
                sh "mvn clean install"
              }
			  
			  dir("Angular") {
                sh "npm install && ng build --prod"
              }
            }
        }
		
		stage('Start test image') {
			steps {
					  sh "/usr/bin/docker-compose build"
					  sh "/usr/bin/docker-compose up -d"
					}

		}
		
		stage('E2E Tests') {
			steps {
				sh "echo e2e"
			}
		}
    }
	
	post {
      always {
		sh "/usr/bin/docker-compose down || true"
      }
    }
}
