pipeline{
    agent any
    tools{
        maven 'Maven'
    }
    stages{
        stage('code'){
            steps{
                git 'https://github.com/RAHAMSHAIK007/jenkins-java-project.git'
            }
        }
        stage('Build'){
            steps{
                sh 'mvn compile'
            }
        }
        stage('Test'){
            steps{
                sh 'mvn test'
            }
        }
        stage('Artifacts'){
            steps{
                sh 'mvn package'
            }
        }
        stage('tomcat'){
            steps{
                deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: 'tomcat', path: '', url: 'http://15.252.140.106:8080/')], contextPath: 'netflix', war: 'target/*'
            }
        }
    }
}
