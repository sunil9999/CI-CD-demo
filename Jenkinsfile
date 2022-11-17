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
	    // This step should not normally be used in your script. Consult the inline help for details.
withCredentials([string(credentialsId: 'dockerhub', variable: 'dockerhub1')]) {
	sh 'docker login -u sunilraju99 -p ${dockerhub1}'
    // some block
}
		sh 'docker push sunilraju99/my-webapp:1.0'
		}
		}
		}
	}
	
  

    
