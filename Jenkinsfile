pipeline {
    agent any
    stages {
        
        stage('Git Checkout') {
            steps {
                echo 'Checking out from Git repo!'
                git 'https://github.com/StevanMMihajlovic/Jenkins_Pipeline.git'
            }
        }
        
        stage('Build') {
            steps {
                echo 'Building the checked-out project!'
                bat 'Build.bat'
            }
        }
        
        stage('Unit-test') {
            steps {
                echo 'Running Unit tests!'
                bat 'Unit.bat'
            }
        }
        
         stage('Quality Gate') {
            steps {
                echo 'Verifying Quality Gates!'
                bat 'Quality.bat'
            }
        }
        
        stage('Deploy') {
            steps {
                echo 'Deploy ti Stage Environment for more tests!'
                bat 'Deploy.bat'
            }
        }
    }
    post {
        always {
            echo 'This will always run.'
        }
        success {
            echo 'This will run on success.'
        }
        failure {
            echo 'This will run on failure.'
        }
        unstable {
            echo 'This will run when build is unstable.'
        }
        changed {
            echo 'This will run when status of of current build is changed compared to previous one.'
        }
    }
}
