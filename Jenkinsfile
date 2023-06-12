pipeline {
    agent any
    
    stages {
     
        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }
        
        stage('Build') {
            steps {
                sh 'npm run build'
            }
        }
      
        stage('Deploy') {
            steps {
                // You can customize this step based on your deployment strategy
                sh 'npm start'
            }
        }
    }
}
