pipeline {
  agent any
  stages {
    stage ('checkout source code') {
      steps {
        // get source code from git repository
        https://github.com/skarra9821/Java-assignment.git
          }
    }
    stage ('Build') {
      steps {
        //run the following Maven commands.
        sh "export PATH=$PATH:/opt/maven/bin"
        sh "source /etc/profile"
        sh 'mvn -Dmaven.test.failure.ignore=true cleane package'
      }
    }
      
        
