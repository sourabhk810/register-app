pipeline {
    agent { label 'Jenkins-Agent' }
    tools {
        jdk 'java'
        maven 'maven'
    }
    stages{
        stage("Cleanup Workspace"){
                steps {
                cleanWs()
                }


        stage("Checkout from SCM"){
                steps {
                    git branch: 'main', credentialsId: 'github', url: 'https://github.com/sourabhk810/register-app'
                }
        }

        stage("Build Application"){
            steps {
                sh "mvn clean package"
            }

       }

       stage("Test Application"){
           steps {
                 sh "mvn test"
           }
       }
    }
    }
