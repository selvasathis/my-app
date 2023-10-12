pipeline {
    agent any
    stages {
        stage('maven package') {
            steps {
                script {
                    //make the scrip as package
                    sh "${mvnHome}/bin/mvn clean package"
	                sh 'mv target/website*.war target/newapp.war'
                }
            }
        }
    }
}
