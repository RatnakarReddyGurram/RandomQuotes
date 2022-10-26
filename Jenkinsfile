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
        stage('Deploy To DEV') {
            when { tag "*-dev" }
            steps {
                script{
                gitTag = "$TAG_NAME"
                def parts = gitTag.split('-')
                version = parts[0]
                }
                echo "Building $TAG_NAME"
                echo version
                echo 'Deploying only because this commit is tagged...'
                
            }
        }
        stage('Deploy To PREPOD') {
            when { tag "*-main" }
            steps {
                script{
                gitTag = "$TAG_NAME"
                def parts = gitTag.split('-')
                version = parts[0]
                }
                echo "Building $TAG_NAME"
                echo version
                echo 'Deploying only because this commit is tagged...'
                
            }
        }
    }
}
