pipeline {
    agent any
    stages {
        stage('checkout') {
            steps {
                echo 'checkout scm'
              git 'https://github.com/santhoshissa/hello-world-spring-boot.git'
            }
        }
       stage('Build and Package') {
            steps {
                echo 'Build and Package'
                bat 'mvn clean'
                bat 'mvn install'
                //bat 'mvn sonar:sonar -Dsonar.host.url=http://localhost:9000 -Dsonar.login=34b5eb060faf6646063dc8fe6edc8d2bc5fa1363'
            }
        }
         stage('Code Quality with Sonar') {
            steps {
                echo 'Code Quality'
                bat 'mvn sonar:sonar -Dsonar.host.url=http://localhost:9000 -Dsonar.login=34b5eb060faf6646063dc8fe6edc8d2bc5fa1363'
            }
        }
       stage('Deploy') {
            steps {
                echo 'Deploy to Tomcat'
            }
        }
    }  
    tools {
        maven 'mvn'
        jdk 'openjdk'
        git 'git'
    }
}
