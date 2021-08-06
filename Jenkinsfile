pipeline{
        agent any
        environment{
                DOCKER_CREDENTIALS=credentials('DOCKER_CREDENTIALS')
        }
        stages{
            stage('Docker Login'){
                steps{
                    sh "sudo apt-get update"
                    sh "sudo apt-get install apt-transport-https ca-certificates curl gnupg lsb-release"
                    sh "curl -fsSL 'https://download.docker.com/linux/ubuntu/gpg' | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg"
                    sh "echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] 'https://download.docker.com/linux/ubuntu\
                            bionic stable' | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null"
                    sh "sudo apt-get update"
                    sh "sudo apt-get install docker-ce docker-ce-cli containerd.io"
                    sh "sudo usermod -aG docker jenkins"
                    sh "newgrp docker"
                    sh "docker login -u ${'DOCKER_CREDENTIALS_USR'} -p ${'DOCKER_CREDENTIALS_PSW'}"        
                }
            }
        }
}
