pipeline {
    agent any
    triggers {
        pollSCM('* * * * *')
    }
    stages {
        //stage('Test python') {
        //    steps {
        //        sh "pip install --break-system-packages -r requirements.txt"
         //       sh "python3 test.py"

          //  }
       // }
        stage('Build'){
            steps{
                    sh "docker build -t localhost:4000/pythontest:latest ."
                    sh "docker push localhost:4000/pythontest:latest"
            }
        }
        stage('Deploy to Minikube') {
            steps {
                sh "kubectl apply -f /home/misafidiniaina/tp-jenkins/kubernetes/tp-jenkins.yaml"
            }

        }

    }

}