pipeline {
    agent {
        kubernetes {
            defaultContainer 'kaniko'
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
                sh 'uname'
            }
        }
    }
}