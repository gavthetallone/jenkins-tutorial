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
                    sh "sudo rm /usr/share/keyrings/docker-archive-keyring.gpg"
                    sh "curl https://get.docker.com | sudo bash"
                    sh "sudo usermod -aG docker jenkins"
                    sh "newgrp docker"
                    sh "sudo docker login -u ${'DOCKER_CREDENTIALS_USR'} -p ${'DOCKER_CREDENTIALS_PSW'}"        
                }
            }
        }
}
