pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building application...'
                
            }
        }
        stage('Test') {
            steps {
               echo 'Testing application tagged...'
            }
        }
        stage('Deploy') {
            when { tag "release-*" }
            steps {
                echo tag 'release-*'
                echo 'Deploying only because this commit is tagged...'
               
            }
        }
    }
}
