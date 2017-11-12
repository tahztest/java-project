pipeline {
  agent any

  stages {
    stage('build') {
      step {
        sh 'ant -f build.xml -v'
      }
    }
  }

  post {
    always {
      step {
        archive 'dist/*jar'
      }
    }
  }
}
