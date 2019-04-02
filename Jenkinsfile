pipeline {
  agent { label 'demo-build-clr'}
  options {
    timeout(time: 1, unit: 'HOURS')
  }
  stages {
    stage('Build') {
      steps {
        script {
          try{
            echo "Build"
          } catch(err) {
            error("Build Error")
          }
        }
      }
    }
    stage('Check') {
      steps {
        script {
          try{
            echo "Check"
          } catch(err) {
            error("Check Error")
          }
        }
      }

    }
    stage('Clean Up') {
      steps {
        script {
          try{
            echo "Clean up phase"
            sh "cat /etc/os-release"
            sh "hostname"
          } catch(err) {
            error("Clean up Error")
          }
        }
      }

    }
  }

  post {
    always {
      deleteDir()
    }
   }
}
