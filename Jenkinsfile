pipeline {
  agent any
  stages {
    stage('stage 1') {
      parallel {
        stage('Step 1') {
          steps {
            bat 'npm install .'
          }
        }

        stage('Docker') {
          steps {
            bat 'docker build -t myimage .'
            bat 'docker run myimage -p 3000:3000'
          }
        }

      }
    }

    stage('npm start') {
      steps {
        bat 'npm start .'
      }
    }

  }
}