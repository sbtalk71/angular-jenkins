pipeline {
    agent any
    environment {
        NODEJS_HOME = tool 'node22' // Use configured NodeJS tool name
        PATH = "${NODEJS_HOME}/bin:${env.PATH}"
    }
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/sbtalk71/angular-jenkins.git'
            }
        }
        stage('Install Dependencies') {
            steps {
                bat 'npm install'
            }
        }
        stage('Run Tests') {
            steps {
                bat 'npm run test -- --watch=false --browsers=ChromeHeadless'
            }
        }
        stage('Build Angular App') {
            steps {
                bat 'npm run build -- --configuration=production'
            }
        }
        
    }
}
