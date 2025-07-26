pipeline {
    agent any
    environment {
        KUBECONFIG = '/var/lib/jenkins/.kube/config'
    }
    triggers {
        pollSCM('* * * * *')
    }
    stages {
        stage('Build'){
            steps{
                    sh "docker build -t localhost:4000/pythontest:latest ."
                    sh "docker push localhost:4000/pythontest:latest"
            }
        }
        stage('Deploy to Minikube') {
            steps {
                sh "sudo -u misafidiniaina kubectl apply -f kubernetes/tp-jenkins.yaml"
            }

        }

    }

}
