pipeline{
    agent any
    tools{
        maven 'maven_3_8_7'
    }
    stages{
        stage('CompileandRunSonarAnalysis'){
            steps{
                withCredentials([string(credentialsId:'tech365token',variable:'tech365token')]) {
                sh 'mvn clean verify sonar:sonar -Dsonar.login=$tech365token -Dsonar.organization=tech3651 -Dsonar.host.url=https://sonarcloud.io -Dsonar.projectkey=tech3651'    
            }
        }
    }
}
}