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
            nexusPolicyEvaluation advancedProperties: '', enableDebugLogging: false, failBuildOnNetworkError: false, iqApplication: selectedApplication('23445'), iqInstanceId: 'Nexus_Repo', iqOrganization: '8faff48b35b047dcba1cf8a49479ebf9', iqScanPatterns: [[scanPattern: '**/*.js'], [scanPattern: '**/*.zip']], iqStage: 'build', jobCredentialsId: 'a3b9035f-9881-46fe-85f4-b09ba58af95a'
        }
     }
  }
}
