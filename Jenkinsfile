pipeline {
    agent any
	
	tools { 
        maven 'MAVEN_HOME'
        jdk   'jdk1.8'
    }
	
    docker.image('java:8').inside{
    	stage('test'){
    		echo '********java version**********'
    		sh   'java -version'
    }
  }
}