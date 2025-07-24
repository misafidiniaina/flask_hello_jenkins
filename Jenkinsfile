pipeline {
    agent any
    triggers {
        pollSCM('* * * * *')
    }
    stages {
        stage('Test python') {
            steps {
                sh "pip install --break-system-packages -r requirements.txt"
                sh "python3 test.py"
            }
        }

        stage('Deploy to Minikube') {
            steps {
                // your deployment commands here, e.g. kubectl apply ...
                sh "kubectl apply -f deployment.yaml"
            }
        }
    }
}
