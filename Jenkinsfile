pipeline {
    agent any
        tools {
        gradle "Default"
    }
    stages {
        stage("Build Gradle") {
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
