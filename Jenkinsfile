pipeline {

  agent any

  stages {

    stage('PULL') {
     steps {
        echo "Getting Project from Git"; 
				git(url: 'https://github.com/samar-b/LivraisonContinue.git', branch: 'main')
			}
}
    
    
   
    stage ('Build')
    {
      steps {
        script{
      
        sh"ansible-playbook ansible/build.yml -i ansible/inventory/host.yml"
        }
      }
    }
    
     stage ('docker')
    {
      steps {
        script{
        sh"ansible-playbook ansible/docker.yml -i ansible/inventory/host.yml"
        }
      }
    }
    
    stage('Login Dockerhub')
    {
        steps {
            sh 'docker login -u samarbelhadj -p Samar123**'
        }
    }
    
     stage ('docker registry ')
    {
      steps {
        script{
        sh"ansible-playbook ansible/docker-registry.yml -i ansible/inventory/host.yml"
        }
      }
    }







  }

}
