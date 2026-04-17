pipeline {
    agent any

    stages {
        stage('Build and Package') {
            steps {
                dir('ct5209_test1Maven') {
                    sh 'mvn clean package'
                }
            }
        }
    }

    post {
        success {
            archiveArtifacts allowEmptyArchive: true, artifacts: 'ct5209_test1maven/target/*.jar'
        }
    }
}
