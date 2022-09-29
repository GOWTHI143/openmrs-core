pipeline {
    agent {label 'jdk-11'}
    stages {
        stage('vcs') {
            steps {
                git url: 'https://github.com/GOWTHI143/openmrs-core.git',
                    branch: 'master'
            }
        }
        stage('build') {
                steps {
                    sh 'mvn clean package'
                }
        }
        stage('archive') {
                    steps {junit '**/surefire-reports/*.xml' }
        }

        stage('artifacts') {
                    steps {archiveArtifacts artifacts: 'target/*.jar' }
        }
    }
}
