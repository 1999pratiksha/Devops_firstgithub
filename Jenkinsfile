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
                git branch :'main',
                url: 'https://github.com/1999pratiksha/Devops_firstgithub.git'

                //through jenkins snippet generator
                // checkout scmGit(branches: [[name: '*/main']],
                //  userRemoteConfigs: [[url:'https://github.com/1999pratiksha/Devops_firstgithub.git']])
        
            }
        }

        stage('Build'){
            steps{
                script{
                    try{
                        echo "Building ${APP_NAME}"
                        echo "Version: ${params.APP_VERSION}"
                        sh 'echo "Running build"'
 
                    }
                    catch(Exception e){
                        echo "Build Failed"
                        echo "Error: ${e.getMessage()}"
                        currentBuild.result="FAILURE"
                        throw e
                    }
                }
                
            }
        }
        stage('Parallel test'){
            parallel {
                stage('UI Tests'){
                    steps{
                        script{
                            echo "Running API tests"
                            try{
                                sh ''' echo "Executing API test"
                                echo "Successfully executed API test"
                                '''
                            }
                            catch(Exception e){
                                echo "API test failed"
                                echo "Error:${e.getmessage()}"
                                throw e
                            }
                            
                        }
                    }

                    
                }
            }
            
        }



    }
}
