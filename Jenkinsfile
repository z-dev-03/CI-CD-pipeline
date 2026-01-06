pipeline {
    agent any
    stages {
        stage('Setup') {
            steps {
                bat 'c:\Users\admin\AppData\Local\Programs\Python\Python312\python.exe -m pip install -r requirements.txt'
            }
        }
        stage('Build & Test') {
            steps {
                bat 'c:\Users\admin\AppData\Local\Programs\Python\Python312\python.exe ml_pipeline.py'
            }
        }
        stage('Deploy') {
            steps {
                bat 'c:\Users\admin\AppData\Local\Programs\Python\Python312\python.exe deploy.py'
            }
        }
    }
    post {
        success { 
            echo ' CI/CD SUCCESS - Model Deployed' 
        }
        failure { 
            echo ' CI/CD FAILED' 
        }
    }
}
