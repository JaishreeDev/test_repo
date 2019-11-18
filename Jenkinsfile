#!/usr/bin/env groovy
pipeline {
    agent any
    stages {
        stage('Example') {
            steps {
                echo 'Running ${BUILD_NUMBER} on ${env.JENKINS_URL}'
            }
        }
    }
}