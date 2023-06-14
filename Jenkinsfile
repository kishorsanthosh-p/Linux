pipeline {
    agent any
    
    stages {
       stage("build") {
            steps {
                sh "docker build -t react-jenkins:latest . "
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
        stage('Cleanup') {
            steps {
                script {
                    // Kill the running process
                    try {
                        def process = sh(script: 'your-command-to-kill-process', returnStatus: true)
                        if (process != 0) {
                            error("Failed to kill the process. Exit code: ${process}")
                        }
                    } catch (Exception e) {
                        error("Error while killing the process: ${e.getMessage()}")
                    }
                }
            }
       
    }
}
