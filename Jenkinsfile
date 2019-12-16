pipeline{
    agent any
    environment {
        TODAY = sh(script: "date +%Y-%m-%d_%H-%M-%S", returnStdout: true).trim()
    }
    stages{
        stage('Remove the existing downloaded build files'){
            steps{
                sh '''
                    mkdir test1234
                    mkdir $TODAY
                '''
            }
        }
    }
}
