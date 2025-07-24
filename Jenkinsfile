pipeline {
<<<<<<< HEAD
    agent {
        kubernetes {
            label 'jenkins-agent-my-app'
            yaml """
apiVersion: v1
kind: Pod
metadata:
  labels:
    component: ci
spec:
  containers:
    - name: python
      image: python:3.7
      command:
        - cat
      tty: true
"""
        }
    }

    stages {
        stage('Test python') {
            steps {
                container('python') {
                    sh "pip install -r requirements.txt"
                    sh "python test.py"
                }
=======
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
>>>>>>> 14c80af8192ab88682905a09734a124410d7236d
            }
        }
    }
}
<<<<<<< HEAD

=======
>>>>>>> 14c80af8192ab88682905a09734a124410d7236d
