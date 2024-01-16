pipeline {
    agent any 
    stages {
        stage('Clone repository') {
            steps {
                sh 'git clone  https://github.com/girijans/helloJava.git'
                sh 'pwd'
                }
        }
        stage('Run SonarScanner') {
            steps {
                sh 'docker run -v ./:/root/src --link sonarqube sonarsource/sonar-scanner-cli -D sonar.host.url=http://sonarqube:9000 -D sonar.scm.provider=git -D sonar.projectBaseDir=/root/src -D sonar.sources=. -D sonar.projectName=dotnetcore_demo_sonar -D sonar.token=squ_30dbe20534473e88792eb94c3c55efdb5dfa04f9 -D sonar.projectKey=dotnetcore_demo_sonar'
            }
        }
    }
}
