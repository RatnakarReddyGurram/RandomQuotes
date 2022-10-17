def gitTag = null
def verison = null
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
                script{
                gitTag = "$TAG_NAME"
                def parts = gitTag.split('-')
                version = parts[1]
                }
                echo "Building $TAG_NAME"
                echo version
                echo 'Deploying only because this commit is tagged...'
                
            }
        }
    }
}
