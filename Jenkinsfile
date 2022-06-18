pipeline {
    agent any

    stages {
        stage('Compile') {
            steps {
                dir("servicios/Curso-Microservicios"){
                    sh "docker build -t microservicio ."
                }
            }
        }
        stage('DBDeploy') {
            steps {
                sh "docker images"
            }
        }
    }
}