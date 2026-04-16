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
                dir('mygradleapp') {   // ✅ FIX
                    sh './gradlew build'
                }
            }
        }

        stage('Test') {
            steps {
                dir('mygradleapp') {   // ✅ FIX
                    sh './gradlew test'
                }
            }
        }

        stage('Run Application') {
            steps {
                dir('mygradleapp') {   // ✅ FIX
                    sh './gradlew run'
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

