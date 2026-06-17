pipeline {
  agent any
  tools {
  maven 'Maven'
  }
  stages {
    stage ('Checkout') {
      steps {
        git branch:'master', url:'https://github.com/rochith11/Selenium1.git'
      }
    }
    stage ('Build') {
      steps {
        sh 'mvn clean package'
      }
    }
    stage ('Run Application') {
      steps {
        sh '''
        echo "Starting Application"
        nohup java -jar target/Selenium-1.0-SNAPSHOT.jar > app.log 2>&1 &
        '''
      }
    }
  }
}
