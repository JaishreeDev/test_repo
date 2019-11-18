pipeline {
   agent none
   environment {
       color = "blue"
   }
   stages {
       stage('first') {
            agent any
            steps {
               sh "printenv | sort"
            }
        }
    }
}
