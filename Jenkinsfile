pipeline {
    agent any
    
    stages {
       stage("build") {
            steps {
                sh "docker build -t react-jenkins:latest . "
            }
        }
                stage('Cleanup') {
            steps {
                
                 script {
                    // Find the process ID occupying port 3000
                    def processId = sh(script: "lsof -t -i :3000", returnStdout: true).trim()
                    
                    if (processId) {
                        // Kill the process
                        try {
                            sh "kill ${processId}"
                        } catch (Exception e) {
                            error("Error while killing the process on port 3000: ${e.getMessage()}")
                        }
                    } else {
                        echo "No process found on port 3000"
                    }
                }
                
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
                
                sh "docker ps -a"
                
//                 script {
//                     def portNumber = 3000
//                     def processId = sh(returnStdout: true, script: "lsof -t -i:3000").trim()
//                     sh "kill ${processId}"
//                 }
          sh "docker run -d -p 3000:3000 react-jenkins:latest"
            }
        }
// stage('Cleanup') {
//             steps {
//                 script {
//                     // Kill the running process
//                     try {
//                         sh 'pkill your-process-name'
//                     } catch (Exception e) {
//                         error("Error while killing the process: ${e.getMessage()}")
//                     }
//                 }
//             }
//         }
    }
}
