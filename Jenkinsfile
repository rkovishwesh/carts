pipeline {
    agent any
    
    tools{
      maven 'Maven'
    }	

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
		sh 'mvn clean compile'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
		sh 'mvn test'
            }
        }
        stage('Package') {
            steps {
                echo 'Packaging....'
		sh 'mvn -DskipTests package'
		 archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true
            }
        }
    }
}
