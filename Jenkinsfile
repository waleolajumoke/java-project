pipeline{
    agent any
    tools{
        maven 'maven_3_8_7'
    }
    stages{
        // stage('CompileandRunSonarAnalysis'){
            
        //     steps{
        //        withCredentials([string(credentialsId: 'tech365token', variable: 'tech365token')]) {
        //            sh 'mvn clean package sonar:sonar -Dsonar.login=$tech365token -Dsonar.host.url=https://sonarcloud.io -Dsonar.projectKey=tech3651 -Dsonar.organization=tech3651'
                
        //        }
        //     }
        // }

        // // build docker image
        // stage('BuildDockerImage'){
        //     steps{
        //     withDockerRegistry([credentialsId: "dockerlogin", url:""]){
        //         script{
        //            app =  docker.build("tech365app")
                 
        //         }
        //     }
        //     }
        // }

        // // push docker image
        // stage('PushDockerImage'){
        //     steps{
        //     script{

        //         // docker.withRegistry('https://registry.hub.docker.com', 'dockerlogin'){


        //         docker.withRegistry('https://222634367210.dkr.ecr.us-east-1.amazonaws.com', 'ecr:us-east-1:aws-credentials'){
  
        //             app.push("latest")
        //         }
        //     }
        // }

        // }

        stage('kubernetes deployment'){
            steps{
                withKubeConfig([credentialsId: 'kubelogin']){
                    sh('kubectl delete all -n devsecops')
                    sh ('kubectl apply -f deployment.yaml --namespace=devsecops')
                }
            }
            
        }
    }
}
