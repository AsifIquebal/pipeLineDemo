pipeline {
    agent any
    stages {
        script {
            if (isUnix() == true) {
                echo 'Unix'
            }
            else {
                echo 'Non Unix'
            }
         }
        stage('Cleaning Stage') {
            steps {
                withMaven(maven : 'MAVEN_HOME') {
                    bat 'mvn clean'
                }
            }
        }
        stage('Testing Stage') {
                  steps {
                      withMaven(maven : 'MAVEN_HOME') {
                          bat 'mvn test'
                      }
                  }
        }

    }
    post {
        always {
            echo 'I will always say Hello again!'
        }
    }

}