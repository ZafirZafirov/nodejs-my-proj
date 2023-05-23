pipeline{
    agent{
        label "docker_slave_666"
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
    }
}