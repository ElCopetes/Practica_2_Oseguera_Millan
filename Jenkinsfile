pipeline {
    agent any
    stages {
        stage('Info') {
            steps {
                echo "Build #${env.BUILD_NUMBER}"
                sh 'ls -la'
            }
        }
        stage('Validar HTML') {
            steps {
                sh 'test -f index.html'
                sh 'grep -q "<title>" index.html'
                echo 'index.html existe y tiene <title>'
            }
        }
        stage('Archivar') {
            steps {
                archiveArtifacts artifacts: 'index.html'
            }
        }
    }
}