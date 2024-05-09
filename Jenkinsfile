pipeline {

    agent any

    stages {

        stage('Build') {

            steps {

                sh 'echo "Building..."'

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

            steps {

		skip "this stage is skipped"			
                sh 'echo "Deploying..."'



           }

        }

    }

}
