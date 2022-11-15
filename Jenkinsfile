pipeline
{
    agent any
    stages {
        stage ('Pull'){
            steps{
                script{
                    checkout([$class: 'GitSCM', branches: [[name: '*/main']],
                        userRemoteConfigs: [[
                            credentialsId: 'MyGithub',
                            url: 'https://github.com/amine-souki/Continious_Delivery.git']]])
                }
            }
        }
     }
}
