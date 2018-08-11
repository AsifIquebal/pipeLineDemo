
pipeline {
    agent any
    stages {
        stage('Cleaning Stage') {
            steps {
                if(isUnix()){
                    echo "Unix System"
                }
                else{
                    echo "Non Unix System"
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