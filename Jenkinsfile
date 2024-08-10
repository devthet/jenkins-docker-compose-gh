pipeline{
    agent { label 'windows-agent'}
    stages{
        stage("Verify tools for docker compose"){
            steps{
                bat '''
                    docker version
                    docker info
                    docker compose version
                   
                '''

            }
        }
    }

}