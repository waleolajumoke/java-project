pipeline{
    agent any
    tools{
        maven 'maven_3_8_7'
    }
    stages{
        stage('CompileandRunSonarAnalysis'){
            steps{
                withCredentials([string(credentialsId:'SONAR_TOKEN',variable:'SONAR_TOKEN')]) {
                sh 'mvn clean verify sonar:sonar -Dsonar.login=$SONAR_TOKEN -Dsonar.organization=tech3651 -Dsonar.host.url=https://sonarcloud.io -Dsonar.projectkey=tech3651'    
            }
        }
    }
}
}