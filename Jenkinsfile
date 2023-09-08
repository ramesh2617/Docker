#!groovy
pipeline {
	 agent any
  stages {
  	stage('Maven Install') {
    	agent any {
      	docker {
        	image 'maven:3.5.0'
        }
      }
      steps {
      	sh 'mvn clean install'
      }
    }
  }
}
