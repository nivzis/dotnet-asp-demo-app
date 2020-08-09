pipeline {environment {
    registry = "nivzi/aspapp"
    registryCredential = 'dockerhub'}
	
    agent any

    stages {
        stage('Build') {
            steps {
        sh 'dotnet restore'
        sh 'dotnet msbuild aspnetapp/aspnetapp.csproj'
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
