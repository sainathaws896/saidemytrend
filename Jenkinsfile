
pipeline {
    agent any

    environment {
        PATH = "/opt/maven/bin:$PATH"
    }

    stages {

        stage('Build') {
            steps {
                echo '---build i started ---'
                sh 'mvn clean deploy -Dmaven.test.skip=true'
                echo '--build is completed---'
            }
        }
        stage('Test'){
            steps{
                echo '--unit test is started'
                sh 'mvn surefire-report:report'
                echo 'unit test is completed'
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

