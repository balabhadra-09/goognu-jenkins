pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
                echo 'GitHub source code checkout successful!'
            }
        }

        stage('Build') {
            steps {
                echo 'Building application...'
                sh 'ls -la'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing application...'
                sh 'test -f index.html'
                sh "grep -q 'Goognu Jenkins CI/CD' index.html"
            }
        }

      stage('Deploy') {
    steps {
        sh '''
            cp index.html /var/www/goognu-jenkins/index.html
            echo "Application deployed successfully!"
        '''
    }
}
    }

    post {
        success {
            echo 'CI/CD Pipeline completed successfully!'
        }

        failure {
            echo 'Pipeline failed. Check console output.'
        }
    }
}