pipeline {
    agent { label 'first' }
    parameters {
      string defaultValue: 'Gil', description: 'The name of the user ', name: 'Name', trim: false
    }
    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Welcome') {
            steps {
                echo 'Welcome' + ${parameters.Name}
            }
        }
    }
}

