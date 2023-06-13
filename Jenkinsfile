pipeline {
    agent any
    
    stages {
     
        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }
            
//         stage('Deploy') {
//             steps {
//                 // You can customize this step based on your deployment strategy
//                 sh 'npm start'
//             }
//         }
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
