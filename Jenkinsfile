// DO NOT Modify this file
properties([
  [$class: 'BuildDiscarderProperty', strategy: [$class: 'LogRotator', artifactDaysToKeepStr: '', artifactNumToKeepStr: '', daysToKeepStr: '', numToKeepStr: '20']
]]);

// node -> here is the slave or the agent where you want to run the stage
try {
  node {
    stage("Checkout Code") {
      checkout scm //checking out code
      stash name:'sources', useDefaultExcludes: false
    }
  }

  node {
    unstash 'sources'      
    stage("Maven Build") {
      sh "ls -ltr"
      echo "hello"
    }
  }

  node {
    stage("Docker Build") {
      sh "ls -ltr"
      echo "hello"
    }
  }
  
  node {
    stage("Print Hello") {
      echo "hello"
    }
  }
} catch (Exception ex) {
  throw ex
}
