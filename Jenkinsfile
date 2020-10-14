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
        stage('nexus upload') {
            steps {
            	echo 'nexus upload'
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