pipeline {
    agent any

    stages {
        stage('continuous download') {
            steps {
                git 'https://github.com/kliakos/sparkjava-war-example.git'
            }
        }
         stage('continuous build') {
            steps {
                sh 'mvn install'
            }
        }
        stage('continuous deploy') {
            steps {
                sh 'sshpass -p "chandu" scp target/sparkjava-hello-world-1.0.war chandu@172.17.0.3:/opt/apache-tomcat-9.0.56/webapps'
            }
        }
    }
}
