pipeline {
  environment {
    JAVA_HOME = '/var/jenkins_home/tools/hudson.model.JDK/Java17/jdk-17.0.10/bin'
     PATH = '/var/jenkins_home/tools/hudson.model.JDK/Java17/jdk-17.0.10.jdk/bin:/var/jenkins_home/tools/hudson.tasks.Maven_MavenInstallation/maven-3/bin'
  }
  agent any
  tools {
    maven 'maven-3'
    jdk 'Java17'
  } 
  stages {
    stage('Cloning Git') {
      steps {
        git branch: 'main', changelog: false, poll: false, url: 'https://github.com/todd-duck/duck-clinic.git'
      }
    }
    stage('Compile') {
       steps {
         sh 'mvn compile' //only compilation of the code
       }
    }
  }
}