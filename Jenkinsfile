pipeline {
    agent any
        tools {
        gradle "Default"
    }
    stages {
        stage("Build Gradle") {
            steps {
                sh 'gradlew build'
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
