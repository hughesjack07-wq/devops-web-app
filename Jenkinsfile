pipeline {
    agent any

    stages {
        stage('Build and Package') {
            steps {
                dir('ct5209_test1maven') {
                    sh 'mvn clean'
                    sh 'mvn dependency:copy-dependencies'
                    sh 'mvn compiler:compile'
                    sh 'mvn package'
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
