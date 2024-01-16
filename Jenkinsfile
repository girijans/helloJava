pipeline {
    agent any
    stages {
        stage('Clone repository') {
            steps {
                // sh 'git clone  https://github.com/girijans/helloJava.git'
                sh 'pwd'
                }
        }
        stage('Run SonarScanner') {
            steps {
                sh 'docker run -v ./:/root/src --link sonarqube sonarsource/sonar-scanner-cli -D sonar.host.url=http://sonarqube:9000 -D sonar.scm.provider=git -D sonar.projectBaseDir=/root/src -D sonar.sources=. -D sonar.projectName=java_test -D sonar.token=squ_30dbe20534473e88792eb94c3c55efdb5dfa04f9 -D sonar.projectKey=java_test'
            }
        }
        stage('Run container') {
            steps {
                sh 'docker build -t helloworldjava .'
                sh 'docker run -it helloworldjava'
                sh 'docker ps'
                sh 'docker ps -a'
            }
        }
    }
}
