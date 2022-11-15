node {
  agent any
  
  tools
  {
    maven "Maven"
  }
  stages {
    stage ('checkout') {
      steps {
        git branch: 'main', 'https://github.com/sunil9999/CI-CD-demo.git'
      }
      }
    stage ('Excute Maven') {
      steps {
        sh 'mvn package'
      }
    }
  }
}
    
