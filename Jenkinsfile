pipeline{
    agent any
    environment {
        TODAY = sh(script: "date +%Y-%m-%d_%H-%M-%S", returnStdout: true).trim()
    }
    stages{
        stage('notification'){
            steps{
                sh '''
                   echo "build started"                     
                '''
            }
        }        
    }
    post{
        success{
            build(job: "dgnu_cd/",
            parameters: [string: 'GITHUB_BRANCH', value: env.BRANCH_NAME])        
        }    
    }
}
