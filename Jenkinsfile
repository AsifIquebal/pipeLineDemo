
pipeline {
    agent any
    stages {
        stage('Cleaning Stage') {
            steps {
                script {
                    if (isUnix() == true) {
                            echo 'Unix'
                        }
                        else {
                            echo 'Non Unix'
                    }

                withMaven(maven : 'MAVEN_HOME'){
                    bat 'mvn clean'
                }
            }
        }
        stage('Testing Stage') {
              steps {
                  withMaven(maven : 'MAVEN_HOME'){
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