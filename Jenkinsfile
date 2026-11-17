
pipeline {
    agent any

    stages {

        stage('Download Code') {
            steps {
                echo 'Getting portfolio source code'
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Building portfolio website'
                sh 'test -f index.html'
                sh 'test -f style.css'
                echo 'Build completed successfully!'
            }
        }

        stage('Test') {
            steps {
                echo 'Checking website files'
                sh 'grep -q "My Portfolio" index.html'
                echo 'Website test passed!'
            }
        }

    }

    post {
        success {
            echo 'Portfolio build successful!'
        }

        failure {
            echo 'Portfolio build failed!'
        }
    }
}
