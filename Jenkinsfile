pipeline {
   agent any

   environment {
      input_params = get_param()
      PATH = "C:\\WINDOWS\\SYSTEM32"
	  workspace = "${workspace}"
	  env = "${env.env}"
    }

   stages {
      stage('start') {
          //agent any
         steps {
            echo 'Hello World'
            echo "Workspace: ${workspace}"
            //bat '%AWS_CLI_PATH%'
            bat "%AWS_CLI_PATH% configure list"
            bat "%AWS_CLI_PATH% cloudformation create-stack --stack-name S3BucketStack --template-body file://\"${workspace}\"/S3TemplateOne.json --parameters file://\"${workspace}\"/S3Param.json"
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

/*def func() {
  sh 'aws configure list'

}*/
