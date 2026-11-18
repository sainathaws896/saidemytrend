pipeline{
    agent any
    environment{
        PATH="/opt/maven/bin:$PATH"
    }
    stages{
        stage('build'){
            sh 'mvn clean package'
        }
        stage('SonarQube analysis'){
            environment{
                scannerHome = tool 'sainathaws-sonarqube-scanner' 
            }
            steps{
                withSonarQubeEnv('sainathaws-sonarqube-server')
                sh "${scannerHome}/bin/sonar-scanner"
                
            } 
            
        }
    }
}

