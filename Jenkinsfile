pipeline {
  agent { label 'WIndows' }
  stages {
    stage('Source') { 
      steps {
        checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/gouthamvt/jenkins.git']]])
      }
    }
    stage('Compile') { 
      tools {
        jdk 'JDK8'
        maven 'apache-maven-3.6.1'
      }
        powershell 'java -version'
        powershell 'mvn -version'
	def project_path = "spring-boot-samples/spring-boot-sample-atmosphere"    
        dir(project_path)
    	{
        powershell 'mvn clean package'
      }
    }
  }
}


