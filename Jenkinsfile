pipeline{
    aagent{
        lable "jenkins-gent"
    }
    stages{
        stage("Checkout from SCM"){
            steps{
                git branch: 'main', credentialsID: 'github', url: 'https://github.com/sagar-amd/complete-prodcution-e2e-pipeline'
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