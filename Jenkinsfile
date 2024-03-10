pipeline{
    agent{label 'Jenkins-Agent'}
    tools{
        jdk 'Java17'
        maven 'Maven3'
    }

    stages{
        stage("Cleanup Workspace")
        steps {
            cleanWs()
        }

        stage("Checkout from SCM"){
            steps{
                git branch: 'main', credentialsId: 'github', url: 'https://github.com/Gabinsime75/Project_06-Deploy-to-Kubernetes-Using-Jenkins--Register-App'
            }
        }

        stage("Build Application"){
            steps{
                sh "mvn clean package"
            }
        }

        stage("Test Application"){
            steps{
                sh "mvn test"
            }
        }
    }
}
