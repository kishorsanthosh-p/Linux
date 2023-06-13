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
//                 docker run -itd -p "3000:3000" sptingboot-web:latest 

//             }
//         }
        stage('Run') {
            steps {
                // Run the React development server in a Docker container
                sh 'docker run -p 3000:3000 -itd react-web:latest'
            }
        }
    }
}
