pipeline {
agent any

```
stages {

    stage('Git Checkout') {
        steps {
            git 'https://github.com/a250062-devops/carrepo.git'
        }
    }

    stage('Build Docker Image') {
        steps {
            bat 'docker build -t car-website:v1 .'
        }
    }

    stage('Deploy with Ansible') {
        steps {
            bat 'ansible-playbook deploy.yml'
        }
    }

    stage('Verify Deployment') {
        steps {
            bat 'docker ps'
        }
    }
}

post {
    success {
        echo 'Website deployed successfully!'
    }

    failure {
        echo 'Deployment failed!'
    }
}
```

}
