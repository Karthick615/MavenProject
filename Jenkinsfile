pipeline {
  agent any
  stages {
    stage('Dev Code Pull') {
      steps {
        echo 'Dev Code Pull'
      }
    }

    stage('Dev Maven Build') {
      steps {
        echo 'Dev Maven Build'
      }
    }

    stage('QA Deploy') {
      steps {
        echo 'QA Deploy'
      }
    }

    stage('QA Tests') {
      parallel {
        stage('QA Tests') {
          steps {
            echo 'QA Tests'
          }
        }

        stage('Web (Code Pull, Run tests)') {
          steps {
            echo 'Code Pull'
            echo 'Run Tests'
          }
        }

        stage('API (Code Pull, Run tests)') {
          steps {
            echo 'Code Pull'
            echo 'Run tests'
          }
        }

      }
    }

    stage('QA Certification') {
      when {
        branch 'master'
      }
      steps {
        echo 'Manual Certification'
        input 'Do you want to Certify QA'
      }
    }

    stage('UAT Deploy') {
      steps {
        echo 'UAT Deploy'
      }
    }

    stage('UAT Certification') {
      when {
        branch 'master'
      }
      steps {
        echo 'Manual UAT Certify'
        input 'Do you want to Certify UAT'
      }
    }

    stage('Prod Deploy') {
      when {
        branch 'master'
      }
      steps {
        echo 'Prod Deploy'
      }
    }

  }
}