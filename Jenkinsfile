pipeline {
    agent any
    stages{
        stage("pull code from github"){
            steps{
                git branch: 'main', changelog: false, poll: false, url: 'https://github.com/Ahammed-2006/python-website-.git'
            }
        }
        stage("docker build"){
            steps{
                sh 'docker build -t flask-app .'
                
            }
        }
        stage("run the container"){
            steps{
                sh 'docker rm -f flask-app|| true'
                sh 'docker run -d -p 5000:5000 --name flask-app flask-app'
            }
        }
    }
}
