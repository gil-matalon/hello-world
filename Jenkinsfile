pipeline {
	agent any
	triggers {
		pollSCM '* * * * *'
	}
	parameters {
      booleanParam defaultValue: true, description: 'Whether to build production', name: 'buildProduction'
    }
	stages {
		stage('Build Dev') {
			environment {
				ENV = "Dev"
			}
			steps {
				echo "Build $env.ENV"	
				sleep 2
			}
		}
		stage ('Build Production') {
		    when { 
		        equals expected: true, actual: params.buildProduction 
		    }
			environment {
				ENV = "Production"
			}
			steps {
				echo "Build $env.ENV"				
			}
		}
	}
}
