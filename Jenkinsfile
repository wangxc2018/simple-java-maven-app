pipeline {
    agent any

    environment {
        GREETING = 'Hello World'
    }

    stages{
        stage('Begin') {
            steps{
                echo "${GREETING}"
                echo "Running ${env.BUILD_ID}"
            }
        }
        stage('Build') {
            steps{
                bat 'mvn -B -DskipTests clean package'
            }
        }
        stage('Test') {
            steps{
                bat 'mvn test'
            }
        }
        stage('Deploy') {
            steps{
                echo 'Deploying...'
            }
        }
   }
   post {
        aborted {
            echo 'Build Aborted!'
        }
        success {
            echo 'Build Success!'
        }
       failure {
           echo 'Build Failure!'
       }
    }
}