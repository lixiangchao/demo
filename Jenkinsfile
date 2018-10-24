pipeline {
    agent any
	
	tools { 
        maven 'MAVEN_HOME'
        jdk   'jdk1.8'
    }
	
	stages{
		stage('test1'){
			docker.image('java:8').inside{
    			echo '********java version**********'
    			sh   'java -version'
		}	
	}
  }
}