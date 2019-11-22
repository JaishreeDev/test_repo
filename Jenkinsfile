pipeline {
  agent any

  //parameters {
  //}

  environment {
      input_params = get_param()
	  
	  /*AWS_DEFAULT_REGION = ${AWS_DEFAULT_REGION}
	  AWS_ACCESS_KEY_ID = "${AWS_ACCESS_KEY_ID}"
	  AWS_SECRET_ACCESS_KEY_ID = "${AWS_SECRET_ACCESS_KEY_ID}"
	  AWS_CLI_PATH = "${AWS_CLI_PATH}"*/
  }

  stages {
    //stage('')

    stage('Start') {
      steps {
	  
		/*withCredentials([[$class: 'UsernamePasswordMultiBinding', credentialsId: 'aws-key', usernameVariable: 'AWS_ACCESS_KEY_ID', passwordVariable: 'AWS_SECRET_ACCESS_KEY_ID']]) {
        aws("--region=eu-west-1")
		sh 'aws s3 ls'
        }*/
		
		echo 'aws configure set AWS_ACCESS_KEY_ID ${env.AWS_ACCESS_KEY_ID}'
		echo 'aws configure set AWS_SECRET_ACCESS_KEY ${env.AWS_SECRET_ACCESS_KEY}'
		echo 'aws configure set AWS_DEFAULT_REGION ${env.AWS_DEFAULT_REGION}'
		echo 'aws configure list'
		echo 'aws s3 ls'
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
