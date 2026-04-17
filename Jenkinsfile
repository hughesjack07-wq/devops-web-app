pipeline {
    agent any

    stages {
        stage('build & package') {
            steps {
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
            archiveArtifacts allowEmptyArchive: true, artifacts: 'ct5209_test1Maven/target/*.jar'
        }
    }
}
