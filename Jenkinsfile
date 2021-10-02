pipeline {
	agent any
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
