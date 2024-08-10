pipeline{
    agent { label 'windows-agent'}
    stages{
        stage("Verify tools for docker compose"){
            steps{
                bat '''
                    docker version
                    docker info
                    docker compose version
                    curl --version
                    jq --version
                   
                '''

            }
        }
        stage('Prune Docker Data'){
            steps{
                bat 'docker system prune -a --volume -f'
            }
        }
        stage('Start Container'){
            steps{
                bat 'docker compose up -d --no-color --wait'
            }
        }
        stage('Run test against the Container'){
            steps{
                bat 'curl http://localhost:3000/param?query=demo | jq'
            }
        }
    }
    post{
        always{
            bat 'docker compose down --remove-orphans -v'
            bat 'docker compose ps'
        }
    }

}