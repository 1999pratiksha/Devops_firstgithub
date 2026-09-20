pipeline
{
    agent any
    parameters{
        choice(
            name:'ENVIRONMENT',
            choices:['DEV','QA','STAGING','PROD'],
            description:'Select the environment for deployment'
        )
        string(
            name: 'APP_VERSION'
            defaultValue: '1.0.0', 
            description: 'Enter application version')
        }

        environment{
            APP_NAME = "Firstpipelinejob"
        }
        
    stages{
        stage('Build'){
            steps{
                echo 'Building application'
            }
        }
        stage('Test'){
            steps{
                echo 'Running tests'
            }
        }
        stage('Deploy'){
            steps{
                echo 'Deploy application'
            }
        }



    }
}