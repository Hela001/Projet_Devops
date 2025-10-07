pipeline {
    agent any

    stages {
        stage('Git Checkout') {
            steps {
                echo "Cloning branch 'hela' from fork Hela001..."
                git branch: 'hela', url: 'https://github.com/Hela001/Projet_Devops.git'
            }
        }

        stage('Build & Test') {
            steps {
                echo 'Build and Test stage running…'
                script {
                    try {
                        // Compile et lance les tests
                        sh 'mvn clean package'
                    } catch (err) {
                        echo "Build or tests failed!"
                        error("Stopping pipeline due to build/test failure.")
                    }
                }
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully ✅'
        }
        failure {
            echo 'Pipeline failed ❌'
        }
    }
}
