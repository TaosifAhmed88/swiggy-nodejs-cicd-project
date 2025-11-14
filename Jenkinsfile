pipeline {
    agent any

tools {
        nodejs "node18"
    }

    stages {

        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM',
                    branches: [[name: '*/main']],
                    userRemoteConfigs: [[url: 'https://github.com/TaosifAhmed88/swiggy-nodejs-cicd-project.git']]
                ])
            }
        }

        stage('Install dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Run tests') {
            steps {
                sh 'npm test'
            }
        }

        stage('Build project') {
            steps {
                sh 'npm run build'
            }
        }
    }
}
