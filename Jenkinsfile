pipeline {
    agent any
    tools{
        maven 'M3_8_6'
    }
    stages {

        stage('Compile') {
            steps {
                dir("servicios/Curso-Microservicios"){
                    sh "docker build -t microservicio ."
                }
            }
        }
        stage('Push images') {
            steps {
                withCredentials([[$class: 'UsernamePasswordMultiBinding', credentialsId: 'docker_nexus', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD']]) {
                    sh 'docker login -u $USERNAME -p $PASSWORD'
                    sh 'docker push microservicio:lastest'
                }
            }
        }
    }
}