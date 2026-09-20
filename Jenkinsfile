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
            name: 'APP_VERSION',
            defaultValue: '1.0.0', 
            description: 'Enter application version'
            )
        }

        environment{
            APP_NAME = "Firstpipelinejob"
        }

    stages{
        stage('Checkout'){
            steps{
                checkout scmGit(branches: [[name: '*/main']],
                 userRemoteConfigs: [[url:'https://github.com/1999pratiksha/Devops_firstgithub.git']])
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