pipeline {
    agent any
    stages {
        stage('Information') {
            steps {
                sh '''
                    pwd
                    whoami
                    date
            '''
            }
        }
        stage('Build') {
            steps {
                sh '''
                    mkdir -p build
                    touch build/app.txt
                    ls -la build
                '''
            }
        }
        stage('Test') {
            steps {
                sh '''
                    test -f build/app.txt
                    echo "Test passed"
                '''
            }
        }
        stage('Deploy') {
            steps {
                sh '''
                    mkdir -p deploy
                    cp build/app.txt deploy/
                    echo "Application deployed successfully"
                '''
            }
        }
    }
    post{
        always{
            echo "ALWAYS WORKED"
        }
        success{
            echo "PIPELINE SUCCESSFUL"
        }
        failure{
            echo "PIPELINE FAILED"
        }
    }
}
