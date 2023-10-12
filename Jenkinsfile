pipeline {
    agent any
    stages {
        stage('maven package') {
            steps {
                script {
                    //make the scrip as package
                    def mvnHome =  tool name: 'maven3', type: 'maven' 
                    sh "${mvnHome}/bin/mvn clean package"
	                sh 'mv target/myweb*.war target/newapp.war'
                }
            }
        }
    }
}
