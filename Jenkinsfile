pipeline{
    agent { label 'windows-agent'}
    stages{
        stage("Verify tools for docker compose"){
            steps{
                sh '''
                    docker version
                    docker info
                   
                '''

            }
        }
    }

}