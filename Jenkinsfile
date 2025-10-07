pipeline {
    agent any

   
    stages {
        stage('Git Checkout') {
            steps {
                echo "Cloning branch 'hela' from fork Hela001..."
                git branch: 'hela', 
                    url: 'https://github.com/Hela001/Projet_Devops.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Build stage running…'
                // Remplace par tes commandes réelles
                script {
                    try {
                        sh 'mvn clean package'  // Exemple Maven build
                    } catch (err) {
                        echo "Build failed!"
                        error("Stopping pipeline due to build failure.")
                    }
                }
            }
        }

        stage('Test') {
            steps {
                echo 'Test stage running…'
                // Remplace par tes commandes réelles
                script {
                    try {
                        sh 'mvn test'  // Exemple Maven test
                    } catch (err) {
                        echo "Tests failed!"
                        error("Stopping pipeline due to test failure.")
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
