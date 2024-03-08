pipeline {
    agent any
    stages{
            stage('Clone repository'){
                    steps{
                        checkout([$class:'GitSCM',
                        branches:[[name:'*/main']],
                        userRemoteConfigs: [[url:'https://github.com/prashiljatakiya/PES2UG21CS211_Jenkins.git']]])
                    }
            }

    stages {
        stage('Build') {
            steps {
              build 'PES2UG21CS211-1'
              sh 'g++ main.cpp -o output'
            }
        }
        stage('Test') {
            steps {
                sh './output'
            
            }
        }
        stage('Deploy') {
            steps {
              eco 'Deployed!'
            }
        }
    }

    post {
        failure {
            error 'Pipeline Failed'
        }
    }
}
