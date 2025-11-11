pipeline {
    agent any
    stages {
        stage ('Clone') {
            steps {
               git branch: 'main', credentialsId: '4c1790a4-0510-4aa2-9d85-a072167e6004', url: 'https://github.com/krishemkrishna/spring-petclinic.git'
            }
        }
        stage('build') {
            steps {
                bat 'mvn clean install'
            }
        }
        stage('test') {
            steps {
                bat 'mvn test'
            }
        }
        stage('generate junit test results') {
            steps {
                junit 'target/surefire-reports/*.xml'
            }
        }
        stage('generate artifacts') {
            steps {
                archiveArtifacts artifacts: 'target/*.jar', followSymlinks: false
            }
        }
    }
}