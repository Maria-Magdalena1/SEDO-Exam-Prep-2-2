pipeline{
    agent any

    stages{
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Maria-Magdalena1/SEDO-Exam-Prep-2-2.git'
            }
        }
        stage("Restore dependencies"){
            
            steps{
               bat 'dotnet restore'
            }
            
        }
        stage("Build the project"){
            
            steps{
               bat 'dotnet build --no-restore'
            }
            
        }
        stage("Run the tests"){
           
            steps{
               bat 'dotnet test --no-build --verbosity normal'
            }
            
        }
    }
    post {
    success {
        echo 'Build and tests passed successfully!'
    }
    failure {
        echo 'Build or tests failed — check the logs!'
    }
}
   
}