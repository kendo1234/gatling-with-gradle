pipeline {
    agent any
        tools {
        gradle "Default"
    }
    stages {
        stage("Clean Gradle") {
            steps {
                sh 'gradle clean'
            }
        }
        stage("Build Gradle"){
            steps {
                sh 'gradle build'
                }
        }
        stage("Run Gatling") {
            steps {
                sh 'gradle gatlingRun'
            }
            post {
                always {
                    gatlingArchive()
                }
            }
        }
    }
}
