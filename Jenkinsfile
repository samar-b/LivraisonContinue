pipeline {

  agent any

  stages {

    stage('PULL') {
     steps {
        echo "Getting Project from Git"; 
				git(url: 'https://github.com/samar-b/LivraisonContinue.git', branch: 'main')
			}
}
    
    
   
    stage('build'){
          steps {

                  script{

                 sh "ansible-playbook ansible/build.yml -i ansible/inventory/host.yml"
                  }


         }
  }


  }

}
