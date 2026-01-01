pipeline {
    agent any

    stages {

        stage('Checkout Code') {
            steps {
                git branch: 'main', url: 'https://github.com/MANAS-JI/NeGD_Official_Project_New.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                echo "Building Docker image..."
                sh 'docker build -t negd-web:${BUILD_NUMBER} .'
            }
    

        stage('Deploy using Docker') {
            steps {
                echo "Deploying Docker container..."
                sh '''
                    docker stop negd_web || true
                    docker rm negd_web || true
                    docker run -d -p 9090:80 --name negd_web negd-web:${BUILD_NUMBER}
                '''
            }
        }
    }
}
