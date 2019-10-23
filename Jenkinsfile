pipeline {
    agent any;
    environment { //环境变量
        GREETING = 'Hello World'
    }
    stages{
        stage('Begin') {
            steps{
                echo "${GREETING}";
                echo "Running ${env.BUILD_ID}"
            }
        }
        stage('Build') {
            steps{
                echo 'Building...'
            }
        }
        stage('Test') {
            steps{
                echo 'Testing...'
            }
        }
        stage('Deploy') {
            steps{
                echo 'Deploying...'
            }
        }
   }
   post { //构建完成后置操作
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