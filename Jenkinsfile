pipeline {
    agent any

    stages {
        stage('clone') {
            steps {
                git branch: 'main', url: 'https://github.com/AwsDevops1432/spring-petclinic.git'
            }
        }
        stage('build') {
            steps {
                bat 'mvn clean install'
            }
        }
		
        stage('test') {
            steps {
                bat 'mvn test'
            }
        }
        stage('generated the test reports') {
            steps {
                junit stdioRetention: 'ALL', testResults: 'target/surefire-reports/*.xml'
            }
        }
        stage('generated the artifacts') {
            steps {
                archiveArtifacts artifacts: 'target/*.jar'
            }
        }
        stage('deploy') {
            steps {
                 echo 'deploy'
            }
        }
    }
}
