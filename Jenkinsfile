pipeline {
    agent any
    stages {
         stage('Build') {
             steps {
                 sh 'echo "Hello World"'
                 sh '''
                     echo "Multiline shell steps works too"
                     ls -lah
                 '''
             }
         }
         stage('Lint HTML') {
              steps {
                  sh 'tidy -q -e *.html'
              }
         }
<<<<<<< HEAD
         stage('Upload to AWS') {
=======
         stage('Security Scan') {
              steps { 
                 aquaMicroscanner imageName: 'alpine:latest', notCompliesCmd: 'exit 1', onDisallowed: 'fail', outputFormat: 'html'
              }
         }
        stage('Upload to AWS') {
>>>>>>> 16ed9c2... new changes on jenkins
            steps {
                withAWS(region:'us-east-1', credentials:'Jenkins-Pipelines-on-AWS') {
                    // do something
                    s3Upload(bucket:"jenkins-pipeline-new", file:'index.html');
                }
            }
        }
    }
}