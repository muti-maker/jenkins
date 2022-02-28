pipeline {
    agent {
        docker { image 'node:16.13.1-alpine'}
    }
    stages {
        stage('build') {
            steps {
                sh 'node --version'
                sh '''
                    echo "Tutorial 2"
                    ls -alh
                '''
                retry(2) {
                    sh 'echo 1'
                }
                timeout(time: 3, unit: 'MINUTES') {
                    sh 'sleep 2'
                }
            }
        }
    }
    post {
        always {
            sh 'pwd'
        }
    }
}
