def pom
pipeline {
  agent any
  stages {
    stage ('checkout source code') {
      steps {
        // get source code from git repository
        git branch: 'main', changelog: false, poll: false, url: 'https://github.com/skarra9821/Java-assignment.git'
          }
    }
    stage ('Build-$pom.version-$pom.artifactId') {
      steps {
        //run the following Maven commands.
        sh '''export PATH=$PATH:/opt/maven/bin
        mvn -Dmaven.test.failure.ignore=true clean package'''
        script {
    // script {
    pom = readMavenPom file: 'pom.xml'
    sh "echo $pom.version"
    sh "echo $pom.artifactId"
              }
            }
      }
    }
  }
