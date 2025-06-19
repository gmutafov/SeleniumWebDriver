pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                checkout scm
            }
        }

        stage('Set up .NET Core') {
            steps {
                bat '''
                    echo Installing .NET SDK 6.0
                    choco install dotnet-sdk -y --version=6.0.100
                '''
            }
        }

        stage('Restore Dependencies') {
            steps {
                bat 'dotnet restore SeleniumBasicExercise.sln'
            }
        }

        stage('Build') {
            steps {
                bat 'dotnet build SeleniumBasicExercise.sln --configuration Release'
            }
        }

        stage('Run TestProject1') {
            steps {
                bat 'dotnet test TestProject1; 

            }
        }
        
        stage('Run TestProject2') {
            steps {
                bat 'dotnet test TestProject2; 

            }
        }
        
        stage('Run TestProject3') {
            steps {
                bat 'dotnet test TestProject3; 

            }
        }
        

        


        post {
            success {
                echo 'Pipeline completed successfully.'
            }
            failure {
                echo 'Pipeline failed.'
            }
        }
    }
}