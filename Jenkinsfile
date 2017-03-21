pipeline {
    agent { docker 'python:2.7.12' }
    stages {
        stage('build') {
            steps {
                sh '''
                    python -c "print 'hello'"
                '''
            }
        }
         stage('Test') {
            steps {
                echo 'Testing'
            }
        }
        stage('Deploy - Staging') {
            steps {
                echo './deploy staging'
                echo './run-smoke-tests'
            }
        }
        stage('Sanity check') {
            steps {
                input "Does the staging environment look ok?"
            }
        }
        stage('Deploy - Production') {
            steps {
                echo './deploy production'
            }
        }
    }
}
