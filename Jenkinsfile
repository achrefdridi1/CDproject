pipeline 
{
    agent any
      stages {
         stage('pull'){
            steps{
              script{
                checkout([$class: 'GitSCM' , branches: [[name: '*/achref-dridi']],
                    userRemoteConfigs:[[
                       url: 'https://github.com/achrefdridi1/CDproject.git']]])
}
}
}
         stage('build'){
            steps{
              script{
                sh "npm install"
                sh "ansible-playbook ansible/roles/build.yml  -i ansible/inventory/host.yml -e 'ansible_become_password=ansible' -vvv "

}
}
}  
	stage ('docker'){
	   steps{
	     script{
		sh "ansible-playbook ansible/docker.yml  -i ansible/inventory/host.yml -e 'ansible_become_password=ansible'     "
		
}
}
}    
	stage ('docker hub'){
	   steps{
	     script{
		sh "ansible-playbook ansible/docker-registry.yml  -i ansible/inventory/host.yml -e 'ansible_become_password=ansible'     "
}
}
}
stage ('Monitoring'){

}




}
}
