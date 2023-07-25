pipeline{
    agent{
        label "jenkins-agent"
    }
    stages{
        stage("Checkout from SCM"){
            steps{
                git branch: 'main', credentialsId: 'github', url: 'https://github.com/sagar-amd/complete-prodcution-e2e-pipeline'
            }
        }
        stage("Build Application"){
            steps{
                sh "mvn clean install"
            }
        }
        stage("Test Application"){
            steps{
                sh "mvn test"
            }
        }
    }
}