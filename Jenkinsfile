pipeline {
    agent any
    stages {
        stage('checkout') {
            steps {
                echo 'checkout scm'
              git 'https://github.com/santhoshissa/hello-world-spring-boot.git'
            }
        }
       stage('Build') {
            steps {
                echo 'Build and Package'
                bat 'mvn clean'
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
