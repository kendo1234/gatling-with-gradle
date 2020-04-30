pipeline {
    agent any
    stages {
        stage("Build Gradle") {
            steps {
                sh 'gradlew clean build'
            }
        }
        stage("Run Gatling") {
            steps {
                sh 'gradlew gatlingRun'
            }
            post {
                always {
                    gatlingArchive()
                }
            }
        }
    }
}
