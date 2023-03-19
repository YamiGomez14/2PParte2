pipeline {
    agent any
    environment {
        access_key = credentials('clavedeaccesopublica')
        secret_key = credentials('clavedeaccesosecreta')
    }
    stages {
        stage('terraform') {
            steps {
                sh '''
                    terraform --version
                    terraform init
                    terraform apply -auto-approve -var "access_key=${access_key}" -var "secret_key=${secret_key}"
                '''
            }
        }
    }
}