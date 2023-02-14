pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                sh 'g++ -o sample_output sample.cpp'
                build job: 'existing-job-name'
            }
        }
        stage('Test') {
            steps {
                sh './sample_output > output.txt'
                sh 'cat output.txt'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deployment Successful'
            }
        }
    }
    post {
        failure {
            echo 'Pipeline Failed'
        }
    }
}
