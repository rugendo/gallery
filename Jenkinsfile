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
        stage('test') {
            steps {
                sh '''
                   npm run test
                   '''
            }
        }
        stage('Deploying to Render') {
            steps {
                sh '''
                   curl -X POST https://api.render.com/deploy/srv-cgbfrl5269v4icrkets0?key=UYqwBbB2fno&ref=03f509a09155ad3ac93db05f9f0f2bdd9e450f6f
                   
                   '''
            }
        }
        stage('End') {
            steps {
                echo 'The build has ended successfully'
            }
        }

    }
}



