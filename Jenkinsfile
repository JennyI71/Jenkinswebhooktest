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
 
	                when{
                expression {params.SKIP_DEPLOY == 'true' }
                }
	      steps {
 
                sh 'cat ./deploy.sh'
 
                sh 'echo "Deploying..."'
 
                sh 'mv testfile.txt /tmp'
 
                sh 'ls -l /tmp'
 
            }
 
        }
 
    }
	parameters {booleanParam(defaultValue: false, description: 'Skip deploy stage', name: 'SKIP_DEPLOY')
}

}




