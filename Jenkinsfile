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
        stage('User Input') {
            steps {
                input('Do you want to proceed?')
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
        stage('Parallel'){
            parallel{
                stage('Process 1'){
                    steps{
                        echo 'Parallel execution: Process 1'
                    }
                }
                stage('Process 2'){
                    steps{
                        echo 'Parallel execution: Process 2'
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