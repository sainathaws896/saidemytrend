
pipeline {
    agent any

    environment {
        PATH = "/opt/maven/bin:${env.PATH}"
    }

    stages {

        stage('Build') {
            steps {
                sh 'mvn clean deploy'
            }
        }

        stage('SonarQube Analysis') {
            environment {
                scannerHome = tool 'sainathaws-sonarqube-scanner'
            }

            steps {
                withSonarQubeEnv('sainathaws-sonarqube-server') {
                    sh "${scannerHome}/bin/sonar-scanner"
                }
            }
        }
    }
}

