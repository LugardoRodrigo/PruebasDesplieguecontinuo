pipeline {
    agent any

    tools {
        nodejs 'node'
    }

    stages {
        stage('Install') {
            steps {
                git branch: 'main', url: 'https://github.com/LugardoRodrigo/PruebasDesplieguecontinuo.git'
                bat 'npm install'
            }
        }

        stage('Test') {
            steps {
                bat 'npm run ng test'
            }
        }

        stage('Build') {
            steps {
                bat 'npm run ng build --base-href="./"'
            }
        }

        stage('Deploy') {
            steps {
                bat 'firebase deploy --token %PUEBAFIRE'
            }
        }
    }

}
