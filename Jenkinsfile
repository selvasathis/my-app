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
        stage ('build docker image') {
            steps {
                script {
                    sh 'docker build -t thendralsathis/myweb:002'
                }
            }
        }
        stage ('run a container') {
            steps {
                script {
                    sh 'docker run -itd --name sathis -p "8085:80" thendralsathis/myweb:002'
                    echo ' container created'
                }
            }
        }
    }
}

