pipeline {
    agent any
    stages {
        stage('Git') {
            steps {
                git branch: 'hela', url: 'https://github.com/eya144/Projet_Devops.git'
            }
        }
        stage('Build') {
            steps {
                echo 'Build stage running…'
            }
        }
        stage('Test') {
            steps {
                echo 'Tests running…'
            }
        }
    }
}
