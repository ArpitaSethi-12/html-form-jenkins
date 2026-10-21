
pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Test HTML File') {
            steps {
                sh 'test -f index.html'
                echo 'TC01 PASSED: HTML file exists'
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
                echo 'TC02-TC06 PASSED: Form fields verified'
            }
        }

        stage('Test Form Validation') {
            steps {
                sh '''
                    grep -q 'required' index.html
                    grep -q 'pattern="[0-9]{10}"' index.html
                    grep -q 'maxlength="10"' index.html
                '''
                echo 'TC07-TC09 PASSED: Validation attributes verified'
            }
        }

        stage('Test Success Message') {
            steps {
                sh '''
                    grep -q 'id="message"' index.html
                    grep -q 'Registration submitted successfully!' index.html
                '''
                echo 'TC10 PASSED: Success message verified'
            }
        }
    }

    post {
        success {
            echo 'ALL AUTOMATED TESTS PASSED!'
        }
        failure {
            echo 'TEST FAILED: Check Console Output'
        }
    }
}
