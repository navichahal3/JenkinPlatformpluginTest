pipeline {
  agent any
 
tools {
    maven 'maven'
    jdk 'jdk'
    git 'git'
  }
 
  stages {
     stage ('Build') {
       steps {
         git url: 'https://github.com/navichahal3/JenkinPlatformpluginTest.git', branch: 'main'
         sh 'mvn clean install'
       }
     }

  }
}
