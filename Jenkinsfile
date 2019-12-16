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
            script{
            echo "${env.WORKSPACE}"
            echo "${env.BRANCH_NAME}"
            build job: 'CD_project-datascape-ui',
            parameters: [ string(name: 'GITHUB_BRANCH', value: env.BRANCH_NAME), 
                          string(name:'CI_WORKSPACE', value: env.WORKSPACE)]
            }
        }    
    }
}
