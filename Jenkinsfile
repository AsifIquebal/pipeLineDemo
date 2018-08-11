if(isUnix()){
    echo "Unix System"
}
else{
    echo "Non Unix System"
}
pipeline {
    agent any
    stages {
        stage('Cleaning Stage') {
            steps {
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