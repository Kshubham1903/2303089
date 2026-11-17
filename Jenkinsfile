
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

                bat 'if not exist index.html exit /b 1'
                bat 'if not exist style.css exit /b 1'

                echo 'Build completed successfully!'
            }
        }

        stage('Test') {
            steps {
                echo 'Checking website files'

                bat 'findstr /C:"My Portfolio" index.html'

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
