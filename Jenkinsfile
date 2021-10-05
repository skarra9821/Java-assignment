def pom
def VERSION
def ARTIFACTID

node {
    
  
    stage ('checkout source code') {
      
        // get source code from git repository
        git branch: 'main', changelog: false, poll: false, url: 'https://github.com/skarra9821/Java-assignment.git'
       pom = readMavenPom file: 'pom.xml'
        VERSION = pom.version
        ARTIFACTID = pom.artifactId
    }

    stage (" Build  ${VERSION}  ${ARTIFACTID}") {
     
        //run the following Maven commands.
        sh '''export PATH=$PATH:/opt/maven/bin
        mvn -Dmaven.test.failure.ignore=true clean package'''
        script {
            pom = readMavenPom file: 'pom.xml'
            sh "echo $pom.version"
            sh "echo $pom.artifactId"
        }
      
    }

  
    stage ('permission') {
      
	 //give input
         input 'Do you want to proceed'
    }
 
}
