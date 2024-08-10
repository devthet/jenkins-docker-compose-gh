pipeline{
    agent windows-agent
    stages{
        stage("Verify tools for docker compose"){
            steps{
                sh '''
                    docker version
                    docker info
                    docker compose version
                    curl --version
                    jq --version
                '''

            }
        }
    }

}