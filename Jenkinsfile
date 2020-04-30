pipeline {
    agent any
        tools {
        gradle "GRADLE_LATEST"
    }
    stages {
        stage("Build Gradle") {
            steps {
                sh 'gradle clean build'
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
