<<<<<<< HEAD
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
=======
pipeline {environment {
    registry = "nivzi/aspapp"
    registryCredential = 'dockerhub'}
	
    agent any

    stages {
        stage('Build') {
            steps {
			dotnet restore
			dotnet publish -c release -o /app --no-restore
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
>>>>>>> 6b5c6d9fd1ae60ee51fa74fc0726738b81a79b66
}