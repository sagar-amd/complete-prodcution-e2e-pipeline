pipeline{
    agent{
        label "jenkins-agent"
    }
    tools {
        jdk 'Java17'
        maven 'Maven3.9.3'
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
        stage("Code analysis"){
            steps{
                withSonarQubeEnv(credentialsId: 'jenkins-sonarQube-token'){
                    sh "mvn sonar:sonar"
                }
            }
        }
    }
}