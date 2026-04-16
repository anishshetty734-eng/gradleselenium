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
                dir('mygradleapp') {
                    sh 'gradle build'   // ✅ FIX
                }
            }
        }

        stage('Test') {
            steps {
                dir('mygradleapp') {
                    sh 'gradle test'    // ✅ FIX
                }
            }
        }

        stage('Run Application') {
            steps {
                dir('mygradleapp') {
                    sh 'gradle run'     // ✅ FIX
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
