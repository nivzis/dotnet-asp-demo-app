pipeline {environment {
    registry = "nivzi/aspapp"
    registryCredential = 'dockerhub'}
	
    agent any

    stages {
        stage('Build') {
            steps {
			sh 'dotnet restore'
			sh 'dotnet publish -c release -o /app --no-restore'
            }
        }
        stage('Building image') {
            steps {
			docker.build registry + ":$BUILD_NUMBER"
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}