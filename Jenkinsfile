pipeline{
        agent any
        environment{
                DOCKER_CREDENTIALS=credentials('DOCKER_CREDENTIALS')
        }
        stages{
            stage('Debug'){
                steps{
                    sh "docker login -u ${'DOCKER_CREDENTIALS_USR'} -p ${'DOCKER_CREDENTIALS_PSW'}"        
                }
            }
        }
}
