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
      withCredentials([[$class: 'UsernamePasswordMultiBinding', credentialsId: 'aws-key', usernameVariable: 'AWS_ACCESS_KEY_ID', passwordVariable: 'AWS_SECRET_ACCESS_KEY_ID']]) {
        AWS("--region=eu-west-1 s3 ls")
      }
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
