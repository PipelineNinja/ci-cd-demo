pipeline {
    agent any
    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main', 
                    url: 'https://github.com/PipelineNinja/ci-cd-demo.git',
            }
        }
        stage('Build Project') {
            steps {
                sh 'touch app.jar' // Simulating a build process (creates a fake JAR file)
                sh 'echo "Build complete!"'
            }
        }
        stage('Archive Build') {
            steps {
                archiveArtifacts artifacts: 'app.jar', fingerprint: true
            }
        }
    }
}
