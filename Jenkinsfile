pipeline {
    agent any
    stages {
        stage('build') {
            agent {
                docker {
                    image 'node:1.16.4'
                    reuseNode true
                }
            }
            steps {
                sh 'node --version'
                sh '''
                    cat number.txt || echo "?"
                    echo "1" > number.txt
                    ls -alh
                '''
                retry(2) {
                    sh 'echo hostname'
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
