pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Check HTML File') {
            steps {
                sh 'test -f index.html'
                echo 'PASS: HTML file exists'
            }
        }

        stage('Test Form Fields') {
            steps {
                sh '''
                    grep -q 'id="registrationForm"' index.html
                    grep -q 'id="name"' index.html
                    grep -q 'type="email"' index.html
                    grep -q 'id="contact"' index.html
                    grep -q 'type="submit"' index.html
                '''
                echo 'PASS: All required fields exist'
            }
        }
    }

    post {
        success {
            echo 'All tests passed!'
        }
        failure {
            echo 'Tests failed. Check the console output.'
        }
    }
}