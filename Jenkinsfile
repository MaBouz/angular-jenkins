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
                sh "git clone https://github.com/MaBouz/springboot-angular-mysql-docker.git"
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
