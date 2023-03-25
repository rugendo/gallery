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
                   curl -X GET https://api.render.com/deploy/srv-cgbra702qv267ua36ii0?key=90srx0zGqS4
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



