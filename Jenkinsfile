pipeline {
    agent any 

    stages {
        stage('Checkout') {
            steps {
                // Lấy mã nguồn từ hệ thống quản lý mã nguồn (ví dụ: Git)
                git 'https://github.com/CallMeNaul/ThreadditDeployment.git'
            }
        }
    }
    stage('Run Docker Compose') {
            steps {
                script {
                    sh 'docker-compose -f docker-compose.yml up -d'
                }
            }
        }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed.'
        }
    }
}
