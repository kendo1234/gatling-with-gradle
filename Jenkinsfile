pipeline {
    agent any
    stages {
        stage("Build Gradle") {
            steps {
                sh './gradle clean build'
            }
        }
        stage("Run Gatling") {
            steps {
                sh './gradle gatlingRun'
            }
            post {
                always {
                    gatlingArchive()
                }
            }
        }
    }
}
