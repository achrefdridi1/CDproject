pipeline 
{
    agent any
      stages {
         stage('pull'){
            steps{
              script{
                checkout([$class: 'GitSCM' , branches: [[name: '*/achref']],
                    userRemoteConfigs:[[
                       url: 'https://github.com/achrefdridi1/CDproject.git']]])
}
}
}
         stage('build'){
            steps{
              script{
                sh "ansible-playbook ansible/build.yml  -i ansible/inventory/host.yml" 

}
}
}  
	stage ('docker'){
	   steps{
	     script{
s		h "ansible-playbook ansible/docker.yml  -i ansible/inventory/host.yml -e 'ansible_become_password=ansible'     "
}
}
}    
}
}
