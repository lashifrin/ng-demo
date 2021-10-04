pipeline {
    agent any

    //env.PATH = "/Users/leonidshifrin/.nvm/versions/node/v15.0.0/bin:${env.PATH}"

    stages {
        stage('check tools') {
            steps {
                sh "node -v"
                sh "npm -v"
            }
        }

        stage('checkout') {
            steps {
                checkout scm
            }
        }

        stage('npm install') {
            steps {
                sh "npm install"
            }
        }

        stage('unit tests') {
            steps {
                sh "npm test -- --watch=false"
            }
        }

        stage('protractor tests') {
            steps {
                sh "npm run e2e"
            }
        }
    }
}
