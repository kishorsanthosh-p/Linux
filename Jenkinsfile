pipeline {
    agent any
    
    stages {
       stage("build") {
            steps {
                sh "docker build . -t react-jenkins:latest"
            }
        }
     
//         stage('Install Dependencies') {
//             steps {
//                 sh 'npm install'
//             }
//         }
            
//         stage('Deploy') {
//             steps {
//                 // You can customize this step based on your deployment strategy
//                 sh 'npm start'
//                 docker run -itd -p "3000:3000" sptingboot-web:latest 

//             }
//         }
        stage("Run") {
            steps {
                // Run the React development server in a Docker container
                sh "docker run -d -p 3000:3000 react-jenkins:latest"
            }
        }
    }
}
