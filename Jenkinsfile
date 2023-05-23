pipeline{
    agent{
        label "my-ssh-slave"
    }
    tools {
         nodejs 'nodejs'
    }
    stages {
        stage("Clone Repo") {
            steps {
                git branch: 'main', url: 'https://github.com/ZafirZafirov/nodejs-my-proj.git'
            }
        }
        stage("Build") {
            steps {
                sh "npm ci"
            }
        }
        stage("Test") {
            steps {
                sh "npm test"
            }
        }
        stage('Deploy') {
           steps {
                sh "npm install -g forever"
                sh 'forever start src/index.js'
           }
        }
    }
    post {
        always {
            cleanWs()
        }
    }
}