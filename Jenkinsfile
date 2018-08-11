pipeline {
    agent any
    stages {
        stage('Cleaning Stage') {
            steps {
                script {
                    if (isUnix() == true) {
                        echo 'Unix'
                        withMaven(maven : 'MAVEN_HOME') {
                            sh 'mvn clean'
                        }
                    }
                    else {
                        echo 'Non Unix: Assuming its Windows'
                        withMaven(maven : 'MAVEN_HOME') {
                            bat 'mvn clean'
                        }
                    }
                }
            }
        }
        stage('Testing Stage') {
            steps {
                script {
                    if (isUnix() == true) {
                        echo 'Unix'
                            withMaven(maven : 'MAVEN_HOME') {
                                sh 'mvn test'
                            }
                    }
                    else {
                        echo 'Non Unix: Assuming its Windows'
                        withMaven(maven : 'MAVEN_HOME') {
                            bat 'mvn test'
                        }
                    }
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