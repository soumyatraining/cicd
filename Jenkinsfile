pipeline {
    agent any
    stages {
     // adasfddded
        stage('Checkout the Git repository') {
            steps {
                git branch: 'master', url: ' https://github.com/amitopenwriteup/cicd.git'
            }
        }
        stage('Build Docker image') {
            steps {
                script {
                    def dockerfile = 'dockerfile'
                    def registry = 'localhost:5000'
                    def imageName = 'myimage'
                    def imageTag = 'latest'
                    def dockerImage = docker.build("${registry}/${imageName}:${imageTag}", "-f ${dockerfile} .")
                    dockerImage.push()
                }
            }
        }
       stage('Build Docker image') {
            steps {
                script {
                  kubernetesDeploy configs: 'deployment.yaml',kubeconfig(credentialsId: '9445dd9b-e604-40cd-a802-79f747011ecb', serverUrl: 'https://192.168.111.130:6443')
                }
            }
       }
    }
}
