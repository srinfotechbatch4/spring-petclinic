pipeline {
    
    agent any
    
    stages{
        stage('Clone the project'){
            
            steps{
                git branch: 'feature/2025.10.16', url: 'https://github.com/srinfotechbatch4/spring-petclinic.git'
            }
        }
        
        stage('Build'){
            
            steps{
                bat 'mvn clean'
            }
        }
        
         stage('Test'){
            
            steps{
                bat 'mvn test'
            }
        }
        
         stage('Generate the Junit test results'){
            
            steps{
              junit 'target/surefire-reports/*.xml'
            }
        }
         stage('Generate Artifacts'){
            
            steps{
             archiveArtifacts artifacts: 'target/*.jar', followSymlinks: false
            }
        }
    }
}