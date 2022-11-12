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
        sh "npm install --legacy-peer-deps"
        sh"ansible-playbook ansible/build.yml -i ansible/inventory/host.yml"
        }
      }
    }


  }

}
