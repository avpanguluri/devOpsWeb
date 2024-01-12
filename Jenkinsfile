pipeline {
    agent any
    
    tools {
        maven 'cd_maven'
        jdk 'java_11'
    }

stages{
        stage('Build'){
            steps {
                sh 'mvn clean package'
            }
            post {
                success {
                    echo 'Archiving the artifacts'
                    archiveArtifacts artifacts: '**/*.war'
                }
            }
        }
    }
}
