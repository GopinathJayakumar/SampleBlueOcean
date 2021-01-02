pipeline {
  agent any
  stages {
    stage('Development Evn') {
      steps {
        echo 'Make a Connection with your SCM(Git)'
        echo 'Pull the code from your connected Repo'
        echo 'Build the Code in your local'
      }
    }

    stage('Smoke Testing') {
      steps {
        echo 'Run 5 Smoke Tests'
      }
    }

    stage('Deploy QA Env') {
      steps {
        echo 'Stop the Server'
        echo 'Move the new Build from Dev to QA Env'
      }
    }

    stage('Integration Testing') {
      parallel {
        stage('Integration Testing') {
          steps {
            echo 'UI Test - Integrations'
          }
        }

        stage('API Testing') {
          steps {
            echo 'Using REST Call - Automation Test'
          }
        }

        stage('Performance Testing') {
          steps {
            echo 'Using Loadrunner/ Jmeter Test'
          }
        }

      }
    }

    stage('Certify') {
      steps {
        echo 'QA - Certify'
      }
    }

  }
}