pipeline {
    agent { dockerfile true }
    stages {
        stage('build') {
            steps {
                sh '''
                    cat number.txt || echo "?"
                    echo "2" > number.txt
                    ls -alh
                    svn --version
                    node --version
                '''
                retry(2) {
                    sh 'hostname'
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
