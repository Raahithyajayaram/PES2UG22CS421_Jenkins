pipeline {
    agent any
    stages {
         stage('Clone repository') {
             steps {
                 checkout([$class: 'GitSCM',
                 branches: [[name: '*/main']],
                 userRemoteConfigs: [[url: 'https://github.com/Raahithyajayaram/PES2UG22CS421_Jenkins.git']]])
             }
         }

        stage('Build') {
            steps {
                build 'PES2UG22CS421-1'
                sh 'g++ newfile.cpp -o output' 
            }
        }

        stage('Test') {
            steps {
                sh './output'
            }
        }

        stage('Deploy') {
            steps {
                echo 'deploy'
            }
        }
    }
    post {
        failure {
            error 'Pipeline failed'
        }
    }
}
