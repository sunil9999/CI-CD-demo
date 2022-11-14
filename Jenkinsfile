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
    stage ('docker build and tag') {
      steps {
        sh 'docker build -t my-webapp:latest .'
        sh 'docker tag my-webapp sunilraju99/my-webapp:1.0'
      }
    }
  }
}
