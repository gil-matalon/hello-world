pipeline {
	agent any
	triggers {
		pollSCM '* * * * *'
	}
	stages {
		stage ('Parallel') {
			parallel {
				stage('Build Dev') {
					environment {
						ENV = "Dev"
					}
					steps {
						echo "Build $env.ENV"
						sleep 10						
					}
				}
				stage ('Build Production') {
					environment {
						ENV = "Production"
					}
					steps {
						echo "Build $env.ENV"
						sleep 5
					}
				}
			}
		}
	}
}
