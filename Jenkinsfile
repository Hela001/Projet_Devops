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
                script {
                    try {
                        sh 'mvn clean package -DskipTests'  // Compile sans lancer les tests
                    } catch (err) {
                        echo "Build failed!"
                        error("Stopping pipeline due to build failure.")
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
