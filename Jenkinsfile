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
        nohup mvn exec:java -Dexec.mainClass="com.example.App" > app.log 2>&1 &
        '''
      }
    }
  }
}
