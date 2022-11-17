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
        sh 'docker tag my-webapp sunilraju99/my-webapp:1.0'
      }
    }
    stage ('publish image to dockerhub') {
	 steps {	   
        withCredentials([string(credentialsId: 'dockerhub', variable: 'dockerhub1')]) {
	sh 'docker login -u sunilraju99 -p ${dockerhub1}'   
}
		sh 'docker push sunilraju99/my-webapp:1.0'
		}
		}
	  stage('Run Docker container on Jenkins Agent') {
             
            steps 
   {
                sh "docker run -d -p 8003:8080 sunilraju99/my-webapp"
   }
	  }
 
      stage('Run Docker container on remote hosts') {
             
            steps {
                //sh "docker -H ssh://jenkins@172.31.10.0 run sunilraju99/my-webapp"
		    sh "ssh://jenkins@172.31.10.0 docker run sunilraju99/my-webapp"
	    }
      }
            
   }
	  }
	
  

    
