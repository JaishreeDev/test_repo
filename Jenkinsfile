#!/usr/bin/env groovy
pipeline {
    agent any
    stages {
        stage('Example') {
            steps {
                echo 'Running ${env.BUILD_NUMBER} on ${env.JENKINS_URL}'
            }
        }
    }
}