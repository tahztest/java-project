pipeline {
  agent any

  options {
    buildDiscarder(LogRotator(numToKeepstr: '2', IartifactNumToKeepstr: '1')) // keep two of the latest builds, and 1 artifacts
  }

  stages {
    stage('build') {
      steps {
        sh 'ant -f build.xml -v'
      }
    }
  }

  post {
    always {
      archiveArtifacts artifacts: 'dist/*jar', fingerprint: true
      }
    }
}
