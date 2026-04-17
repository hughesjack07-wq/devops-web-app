pipeline {
    agent any
    stages {
        stage('GetProject') {
            steps {
                git 'https://github.com/hughesjack07-wq/devops-web-app.git'
            }
        }
        stage('build') {
            steps {
                dir('ct5209_test1maven') {
                    sh 'mvn clean'
                    sh 'mvn dependency:copy-dependencies'
                    sh 'mvn compiler:compile'
                }
            }
        }
        stage('Package') {
            steps {
                dir('ct5209_test1maven') {
                    sh 'mvn package'
                }
            }
        }
    }
    post {
        success {
            archiveArtifacts allowEmptyArchive: true,
                artifacts: 'ct5209_test1maven/target/*.jar'
        }
    }
}
