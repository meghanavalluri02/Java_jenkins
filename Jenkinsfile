pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/meghanavalluri02/Java_jenkins.git'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Deploy to Tomcat') {
            steps {
                sh 'scp -o StrictHostKeyChecking=no target/*.war master@192.168.203.128:/var/lib/tomcat9/webapps/'
            }
        }
    }
}
