pipeline {
    agent any
	
	tools { 
        maven 'MAVEN_HOME'
        jdk   'jdk1.8'
    }
	
    stages {     
        stage ('Initialize') {
            steps {
                sh '''
                    echo "PATH = ${PATH}"
                    echo "MAVEN_HOME = ${MAVEN_HOME}"
                ''' 
            }
        }        
        stage('Package') {
            steps {
              sh 'mvn clean package'
              sh 'mv -u target/demo-0.0.1-SNAPSHOT.war  docker/demo.war'
            }
        }
        stage('Build') {
            steps {
             sh "sudo docker build -t demo:${GIT_BRANCH} docker/"
        	}
        }
        stage('Push') {
            steps {
             sh "sudo docker tag demo:${GIT_BRANCH} docker.registry.cscloud.com/demo:${GIT_BRANCH} "
             sh "sudo docker push docker.registry.cscloud.com/demo:${GIT_BRANCH}"
            }
        }
    }
}pipeline {
    agent any
	
	tools { 
        maven 'MAVEN_HOME'
        jdk   'jdk1.8'
    }
	
    stages {     
        stage ('Initialize') {
            steps {
                sh '''
                    echo "PATH = ${PATH}"
                    echo "MAVEN_HOME = ${MAVEN_HOME}"
                ''' 
            }
        }        
        stage('Package') {
            steps {
              sh 'mvn clean package'
              sh 'mv -u target/demo-0.0.1-SNAPSHOT.war  docker/demo.war'
            }
        }
        stage('Build') {
            steps {
             sh "sudo docker build -t demo:${GIT_BRANCH} docker/"
        	}
        }
        stage('Push') {
            steps {
             sh "sudo docker tag demo:${GIT_BRANCH} docker.registry.cscloud.com/demo:${GIT_BRANCH} "
             sh "sudo docker push docker.registry.cscloud.com/demo:${GIT_BRANCH}"
            }
        }
    }
}