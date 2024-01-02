pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                script {
                    git 'https://github.com/your_username/your_name.git'
                }
            }
        }

        stage('Build and Publish Docker Image') {
            steps {
                script {
                    docker.build('your_name_usn')
                    docker.withRegistry('https://your-docker-registry/', 'docker-credentials-id') {
                        docker.image('your_name_usn').push('latest')
                    }
                }
            }
        }
    }

    post {
        success {
            echo 'Web application deployed successfully!'
            // Additional post-build actions if needed
        }
    }
}
