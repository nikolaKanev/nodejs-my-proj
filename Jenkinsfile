pipeline {

    agent {
        label'Docker-slave'
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
    }
}
