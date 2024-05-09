pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'echo "Building..."'
                sh 'ls -al'
            }
        }
        stage('Test') {
            steps {
                sh 'echo "Testing..."'
                sh 'pwd'
                sh 'touch testfile.txt'
                sh 'ls -l'
            }
        }
        stage('Deploy') {
            when {
                expression {
                    // Full condition for skipping the Deploy stage
                    def scriptExists = fileExists('./deploy.sh')
                    def tmpDirExists = fileExists('/tmp')
                    return !(scriptExists && tmpDirExists)
                }
            }
            steps {
                sh 'cat ./deploy.sh'
                sh 'echo "Deploying..."'
                sh 'mv testfile.txt /tmp'
                sh 'ls -l /tmp'
            }
        }
    }
}

// Helper function to check if a file exists
def fileExists(filePath) {
    return file(filePath).exists()
}

