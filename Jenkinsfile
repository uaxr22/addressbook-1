pipeline {
    agent any
    stages {
        stage('Compile') {
            steps { 
                sh 'mvn compile'
            }
        }
        stage('test') {
            steps { 
                sh 'mvn test'
            }
        }
        stage('package') {
            steps { 
                sh 'mvn package'
                emailext body: '${BUILD_NUMBER}', subject: 'the Build has completed with Status ${BUILD_STATUS}', to: 'obumi43@gmail.com'
            }
        }
    }
}
