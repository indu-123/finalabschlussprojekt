pipeline {
    agent any
    environment {
        NEXUS_HOST = 'nexus:8081'
    }
    stages {
        stage('MVN compile') {
            steps {
                echo "${WORKSPACE}"
                script{
                    mvn.compile()
                }
            }
         }
        stage('unit tests') {
            steps {
                echo 'unit tests'
            }
         }
        stage('verify sonar:sonar') {
            steps {
            	script{
                    withCredentials([usernamePassword(credentialsId: 'sonar', passwordVariable: 'sonar_password', usernameVariable: 'sonar_user')]) {
                      mvn.verify()
                    }
            	}
            }
        }
        stage('artifact package') {
            steps {
                echo 'artifact package'
            }
        }
        stage('deploy to Nexus') {
            steps {
            	echo 'is deployed'
            }
        }
        stage('integration tests') {
            steps {
            	echo 'integration tests'
            }
        }
    }
}
