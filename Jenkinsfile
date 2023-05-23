pipeline {

    agent {
        label'my-ssh-agent-1'
    }

    tools {
      nodejs 'NodeJS'
        }


    stages {
        stage('Clone Repo') {
            steps {
                git branch: 'main', url: 'https://github.com/nikolaKanev/nodejs-my-proj.git'
            }
        }
        stage('Build') {
            steps {
                sh 'npm ci'
            }
        }
        stage('Test') {
            steps {
                sh 'npm test'
            }
        }
        stage('Deploy') {
            steps {
                sh 'npm install -g forever'
                sh 'forever start src/index.js'
            }
        }
    }
}
