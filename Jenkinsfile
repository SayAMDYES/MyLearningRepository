pipeline {
    agent any

    stages {
        stage('pull') {
            steps {
                echo 'start to pull code from git'
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/SayAMDYES/MyLearningRepository']]])
            }
        }
        stage('build'){
            steps{
                sh 'mvn clean package'
                sh 'mvn install package'
            }
        }
        stage('publish'){
            steps{
                sh 'cd $(pwd)/target'
                sh 'ls'
            }
        }
    }
}
