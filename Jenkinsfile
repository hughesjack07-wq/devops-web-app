pipeline {
    agent any

    stages {
        stage('build') {
            steps {
                sh 'mvn clean:clean'
                sh 'mvn dependency:copy-dependencies'
                sh 'mvn compiler:compile'
            }
        }
        
        stage('Package') {
            steps {
                sh 'mvn package'
            }
        }
    }

    post {
        success {
            archiveArtifacts allowEmptyArchive: true, artifacts: 'target/*.jar'
        }
    }
}
