pipeline {
    agent any
    triggers {
        pollSCM('* * * * *')
    }
    stages {
        stage('Test python') {
            steps {
                sh "pip3 install -r requirements.txt"
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
