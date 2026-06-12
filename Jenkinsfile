pipeline {
agent any

stages {

    stage('Git Checkout') {
        steps {
            git branch: 'main',
                url: 'https://github.com/a250062-devops/carrepo.git'
        }
    }

    stage('Build Docker Image') {
        steps {
            sh 'docker build -t car-website:v1 .'
        }
    }

    stage('Deploy Using Ansible') {
        steps {
            sh 'ansible-playbook deploy.yml'
        }
    }

    stage('Verify Deployment') {
        steps {
            sh 'docker ps'
        }
    }
}

post {
    success {
        echo 'Car Website deployed successfully!'
    }

    failure {
        echo 'Deployment failed!'
    }
}

}
