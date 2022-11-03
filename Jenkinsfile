pipeline 
{
    agent any
      stages {
         stage('pull'){
            steps{
              script{
                checkout([$class: 'GitSCM' , branches: [[name: '*/achref]],
                    userRemoteConfigs:[[
                       url: 'https://github.com/achrefdridi1/CDproject.git']]])
}
}
}
}
}
