pipeline 
{
    agent any
      stages {
         stage('pull'){
            steps{
              script{
                checkout([$class: 'GitSCM' , branches: [[name: '*/master']],
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
}
}
