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
     stage('IQ Policy Evaluation') {
        steps {
            sh 'java -version'
            nexusPolicyEvaluation advancedProperties: '', 
            enableDebugLogging: false, 
            failBuildOnNetworkError: false, 
            iqScanPatterns: [[scanPattern: '**/pom.xml'], [scanPattern: '**/*.jar'], [scanPattern: '**/*.properties']],
            iqApplication: 'local-app', iqInstanceId: 'Nexus_Repo', iqOrganization: '8faff48b35b047dcba1cf8a49479ebf9', iqStage: 'build', jobCredentialsId: ''
        }
     }
  }
}
