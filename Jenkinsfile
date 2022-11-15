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
  }
}
    
