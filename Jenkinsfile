pipeline {
    agent any
    triggers {
        pollSCM('* * * * *')
    }
    stages {
        stage('Test python') {
            steps {
                sh "pip install -r requirements.txt"
                sh "python test.py"
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
