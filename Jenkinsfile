pipeline{
    agent any
    stages{
        stage('Build'){
            steps{
                echo "Building from git"
                sh 'ls -la'
            }
        }
        stage('Test'){
            steps{
                echo "Running tests"
            }
        }
        stage('Deploy'){
            steps{
                echo "Deploying...."
            }
        }
    }
    post{
        always{
            echo "One run completed"
        }
        success{
            echo "Great success! the build passed"
        }
        failure{
            echo "Oh no, something broke"
        }
    }
}