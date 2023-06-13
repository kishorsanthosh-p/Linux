pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                echo 'Building React application...'
                sh 'npm install'
                sh 'npm run build'
            }
        }
        
        stage('Run in Background') {
            steps {
                script {
                    def runInBackground = {
                        sh 'nohup npm start > /dev/null 2>&1 &'
                        echo 'React application is running in the background.'
                    }
                    
                    runInBackground()
                }
            }
        }
    }
}
