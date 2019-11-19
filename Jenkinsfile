pipeline {
   agent none
   environment {
       input_params = get_param()
   }
   stages {
       stage('example') {
            agent { label 'master' }
            steps {
                print("Client:", env.input_params)
            }
        }
    }
}

def get_param() {
    node('master') {
		return env.ENV
    }
}