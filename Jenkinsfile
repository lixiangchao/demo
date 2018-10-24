pipeline {
    agent any
	
	tools { 
        maven 'MAVEN_HOME'
        jdk   'jdk1.8'
    }
	
    node {
    
    	docker.image('java:8').inside{
    	
    		echo '********java version**********'
    		sh   'java -version'
    	}     
    }
    
    stages{
         stage('Package') {
            steps {
              echo '********Build JAR********'
              sh 'mvn clean package'
              sh 'mv -u target/demo-0.0.1-SNAPSHOT.jar  docker/demo.jar'
            }
        }
    }

}