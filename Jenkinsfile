pipeline {
    agent any
    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main', url: 'https://github.com/MANAS-JI/NeGD_Official_Project_New.git'
            }
        }
        stage('Build') {
            steps {
                echo "Building..."
            }
        }
        stage('Deploy to Apache') {
            steps {
                sh '''
                    sudo rm -rf /var/www/html/*
                    sudo cp -r * /var/www/html/
                    sudo systemctl restart apache2
                '''
            }
        }
    }
}
