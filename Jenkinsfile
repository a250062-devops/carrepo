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
            sh 'docker build -t car-website:v1 .'
        }
    }

    stage('Deploy with Ansible') {
        steps {
            sh 'ansible-playbook deploy.yml'
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
