pipeline {
    agent any 
    tools { 
        maven 'maven'
        nodejs 'node'
    }
    stages {
        stage ("Clean up"){
            steps {
                deleteDir()
            }
        }
        stage ("Clone repo"){
            steps {
                sh "git https://github.com/MaBouz/angular-jenkins.git"
            }
        }
        stage ("Generate frontend image") {
            steps {
                 dir("angular-jenkins"){
                    sh "docker build -t angular-app ."
                }                
            }
        }
        stage ("Run docker compose") {
            steps {
                 dir("angular-jenkins"){
                    sh " docker compose up -d"
                }                
            }
        }
    }
}
