// pipeline{
//     agent any
//     stages{
//         stage('Build'){
//             steps{
//                 echo "Building from git"
//                 sh 'ls -la'
//             }
//         }
//         stage('Test'){
//             steps{
//                 echo "Running tests"
//             }
//         }
//         stage('Deploy'){
//             steps{
//                 echo "Deploying...."
//             }
//         }
//     }
//     post{
//         always{
//             echo "One run completed"
//         }
//         success{
//             echo "Great success! the build passed"
//         }
//         failure{
//             echo "Oh no, something broke"
//         }
//     }
// }

// ------- Updated jenkins with faking build --------------------
pipeline{
    agent any
    tools {
        nodejs 'node18'
    }
    stages{
        stage("Install Dependencies"){
            steps{
                sh 'npm install'
            }
        }
        stage("Build"){
            steps{
                sh 'npm run build'
            }
        }
        stage("Test"){
            steps{
                echo "running tests"
                sh 'npm test'
            }
        }
    }
    post{
        success{
            echo "Archiving artifacts"
            archiveArtifacts artifacts: 'dist/**/*', fingerprint: true
        }
    }
}