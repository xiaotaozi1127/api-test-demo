//declarative pipeline
pipeline {
    agent any 

    stages {
        stage('\u270A Unit Test'){
            steps{
                sh "echo  I am stage: Unit Test"
                sh "./gradlew clean build"
            }
        }
        
        stage('\u261D Api Test'){
            steps{
                sh 'echo "I am stage: Api Test"'
            }
        }

        stage('Build package'){
            steps{
                sh "./gradlew -x jar build"
            }
        }

        stage('\u270D  Build image') {
            steps{
                sh 'echo "I am stage: Build image"'
                sh "docker build -t api-demo:v${env.BUILD_NUMBER} ."
            }
        } 

        stage('\u26F1  Deploy to local') {
            steps{
                sh 'echo "-----Deploy stage-----"'
                sh "echo deploy...."
            }
        }         
    }   
}
