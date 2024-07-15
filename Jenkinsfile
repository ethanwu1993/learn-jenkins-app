pipeline {
    agent any

    stages {
        stage('Build') {
      agent {
        docker {
          image 'node:18-alpine'
          reuseNode true
        }
      }
      steps {
        sh '''
                  ls -la
                  node --version
                  npm --version
                  npm ci
                  npm run build
                  ls -la
                '''
      }
        }
        stage('Test') {
      steps {
        sh '''
              pwd
              ls -la
              if test -f "./build/index.html"; then
              echo "File exists."
              else
              echo "File does not exist."
              fi  
              npm test
              a
              '''
      }
        }
    }
}
