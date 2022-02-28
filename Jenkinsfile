pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                sh 'hostname'
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
