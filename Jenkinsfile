pipeline {
    agent any

    tools {
        gradle 'Gradle'
        jdk 'JDK'
    }

    stages {

        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/anishshetty734-eng/gradleselenium'
            }
        }

        stage('Build') {
            steps {
                dir('gradlesele') {   // ✅ FIX
                    sh 'gradle build'
                }
            }
        }

        stage('Test') {
            steps {
                dir('gradlesele') {   // ✅ FIX
                    sh 'gradle test'
                }
            }
        }

        stage('Run Application') {
            steps {
                dir('gradlesele') {   // ✅ FIX
                    sh 'gradle run'
                }
            }
        }

    }

    post {
        success {
            echo 'Build and deployment successful!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}
