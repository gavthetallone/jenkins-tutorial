pipeline{
        agent any
        environment{
                DOCKER_CREDENTIALS=credentials('DOCKER_CREDENTIALS')
        }
        stages{
            stage('Docker Login'){
                steps{
                    sh "sudo apt-get update"
                    sh "sudo apt install curl -y"
                    sh "curl https://get.docker.com | sudo bash"
                    sh "sudo usermod -aG docker ${'whoami'}"
                    sh "newgrp docker"
                    sh "docker login -u ${'DOCKER_CREDENTIALS_USR'} -p ${'DOCKER_CREDENTIALS_PSW'}"        
                }
            }
        }
}
