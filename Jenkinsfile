pipeline {
    agent any
    tools {
        go 'gotest'
    }
    environment {
        GO111MODULE = 'on'
    }
    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/PipelineNinja/ci-cd-demo.git'
            }
        }
        stage('Test') {
            steps {
                sh 'go test ./...'
            }
        }
        stage('Build') {
            steps {
                sh 'go build -o go-webapp-sample .'
            }
        }
        stage('Run') {
            steps {
                sh '''
                    chmod +x go-webapp-sample
                    ./go-webapp-sample &
                '''
            }
        }
    }
}
