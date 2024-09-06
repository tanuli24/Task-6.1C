pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building......'
            }
            post {
                always {
                    mail to: 'chenuperera13@gmail.com',
                         subject: 'Build Status Email',
                         body: 'Build log attached'
                }
            }
        }
        stage('Test') {
            steps {
                echo 'Testing.....'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying.....'
                 }
        }
        stage('Completed') {
            steps {
                echo 'Completed.'
            }
        }
    }
}
