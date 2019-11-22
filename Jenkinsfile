#!groovy

pipeline {
  agent any

  environment {
      input_params = get_param()
  }

  stages {

    stage('Start') {
      steps {
		echo "stupid jenkinsfile"
	  }
	}
	
    stage('Variable') {
      steps {
        echo "Client: ${env.input_params}"
        echo "Workspace: ${workspace}"
      }
    }
	
  }
}

def get_param() {
    node('master') {
		return env.ENV
    }
}
