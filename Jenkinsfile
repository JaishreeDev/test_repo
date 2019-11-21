pipeline {
  agent any

  //parameters {
  //}

  environment {
      input_params = get_param()
  }

  stages {
    //stage('')

    stage('Start') {
      steps {
		aws s3 ls
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
