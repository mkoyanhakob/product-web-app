pipeline {
    agent {
        kubernetes {
            yaml '''
kind: Pod
spec:
    containers:
        - name: busybox
          image: busybox
          command:
            - sleep
            - 99999
            '''
        }
    }

    stages {
        stage('Test 1') {
            steps {
                container('busybox') {
                    sh 'hostname'
                    sh 'uname -a'
                    sh 'apt || true'
                }
            }
        }
        stage('Test 2') {
            steps {
                sh 'hostname'
                sh 'uname -a'
                sh 'apt'
            }
        }
    }
}