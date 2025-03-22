pipeline {
    agent any

    environment {
        VENV = 'venv'
    }

    stages {
        stage('Clone Repo') {
            steps {
                git 'https://github.com/your-username/my-python-app.git'
            }
        }

        stage('Set Up Python Environment') {
            steps {
                sh 'python3 -m venv venv'
                sh './venv/bin/pip install --upgrade pip'
                sh './venv/bin/pip install -r requirements.txt'
            }
        }

        stage('Run Tests') {
            steps {
                sh './venv/bin/python -m unittest discover -s . -p "test_*.py"'
            }
        }
    }

    post {
        success {
            echo '✅ Build succeeded!'
        }
        failure {
            echo '❌ Build failed!'
        }
    }
}
