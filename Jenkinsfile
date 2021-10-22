pipeline{
    agent any
    environment {
        NAME_APP = "wordpress"
        PORT_APP = "8585"
        DIR_DOCKER = "/home/jenkins/workspace/wordpress"
    }
    
    stages {
        stage('Build da imagem'){
            agent { node 'teste' }
            steps {
                git url: 'https://github.com/diegoantoni/docker-wordpress'
                script {
                   dir("$DIR_DOCKER"){
                      sh "docker-composer build"
                      sh "docker-compose up -d"
                   }
                }
            }
        }   
      
    }
}
