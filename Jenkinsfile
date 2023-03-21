pipeline {
    agent any
    
    tools {nodejs "Node"}

    stages {
        stage('Start') {
            steps {
                echo 'The build has started'
            }
        }
        stage('Clone the repository') {
            steps {
                git url: 'https://github.com/rugendo/gallery.git', branch: 'master'
            }
        }
        stage('Install dependencies') {
            steps {
                sh '''
                   npm install
                   '''
            }


        }
        stage('Test') {
            steps {
                sh '''
                   npm run test
                   '''
            }
        }
    }
}
        