pipeline {
   agent any
tools{
    maven 'mvn'
    jdk 'jdk8'
}
   stages {
      stage('checkout') {
         steps {
             checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/Nagen07/spring-petclinic']]])
         }
      }
      stage('Build') {
         steps {
             bat 'mvn clean package'
       }
         }
         stage('staticcodeanalysis') {
         steps {
             bat 'mvn sonar:sonar'
       }
         }
      }
   }
