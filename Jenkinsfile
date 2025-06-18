pipeline {
    agent any

    tools {
        nodejs 'nodejs18' // This must match the name in Global Tool Config
    }

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/mohdsaqib12/react-test-app.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Build Project') {
            steps {
                sh 'npm run build'
            }
        }

        stage('Archive Build Output') {
            steps {
                archiveArtifacts artifacts: 'build/**', fingerprint: true
            }
        }

        // Optional deploy stage can be added here if needed
    }
}
