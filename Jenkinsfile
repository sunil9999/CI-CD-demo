pipeline {
  agent any
  
  tools
  {
    maven "Maven"
  }
  stages {
    stage ('SCM Checkout') {
      steps {
        //git branch: 'main', 'https://github.com/sunil9999/CI-CD-demo.git'
        git branch: 'main', url: 'https://github.com/sunil9999/CI-CD-demo.git'
      }
      }
    stage ('Excute Maven') {
      steps {
        sh 'mvn package'
      }
    }
    stage ('docker build and tag') {
      steps {
        sh 'docker build -t my-webapp:latest .'
        sh 'docker tag my-webapp sunilraju99/my-webapp:latest'
      }
    }
    stage ('publish image to dockerhub') {
	 steps {
	    //withDockerResitry ([ credentialsId: "ID_dockerhub", url: "" ])
		 //withDockerRegistry(credentialsId: 'ID_dockerhub', url: 'https://hub.docker.com/repository/docker/sunilraju99/my-webapp1')
		 withDockerRegistry(credentialsId: 'ID_dockerhub', 'docker login --username xxx --password yyy'){
		sh 'docker push sunilraju99/my-webapp:1.0'
		}
		}
		}
	}
	
  }

    
