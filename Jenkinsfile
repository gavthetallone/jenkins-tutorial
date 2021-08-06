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
            stage('Make Directory'){
                steps{
                    sh "mkdir ~/jenkins-tutorial-test"
                }
            }
            stage('Make Files'){
                steps{
                    sh "touch ~/jenkins-tutorial-test/file1 ~/jenkins-tutorial-test/file2"
                }
            }
        }
}
