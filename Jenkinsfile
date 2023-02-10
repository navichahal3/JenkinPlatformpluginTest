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
         git branch: "main", url: 'https://github.com/navichahal3/JenkinPlatformpluginTest.git'
         sh 'mvn clean install'
       }
     }

  }
}
