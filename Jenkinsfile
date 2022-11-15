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
	stage ('Build'){
            steps{
                script{
                    sh "ansible-playbook ansible/build.yml -i ansible/inventory/host.yml"
                }
            }
        }
	stage ('docker'){
	     steps{
	         script{
		            sh " sudo ansible-playbook ansible/docker.yml -i ansible/inventory/host.yml" 
            }
              
       }
  }	
 }
}
