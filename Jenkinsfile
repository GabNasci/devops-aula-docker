pipeline {
    agent any

    stages {
        stage('Build Containers') {
            steps {
                script {
                    // Step 1: Constrói os containers definidos no docker-compose.yml
                    sh 'sudo docker compose build'
                }
            }
        }

        stage('Start Application') {
            steps {
                script {
                    // Step 2: Inicia os containers
                    sh 'sudo docker compose up -d'
                }
            }
        }
    }

    post {
        always {
            // Limpa os containers e redes criados pelo docker-compose
            sh 'sudo docker compose down'
        }
    }
}
