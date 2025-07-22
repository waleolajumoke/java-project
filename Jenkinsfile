pipeline{
    agent any
    tools{
        maven 'maven_3_8_7'
       
    }
    stages{
        // stage('Build') {
        //     steps {
        //         sh 'mvn clean install -DskipTests'
        //     }
        // }

        // stage('Run Tests') {
        //     steps {
        //         sh 'mvn test'
        //     }
        // }

        // stage('Package') {
        //     steps {
        //         sh 'mvn package'
        //     }
        // }

        // stage('Archive JAR') {
        //     steps {
        //         archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
        //     }
        // }
stage('Build Docker Image') {
    steps {
        sh 'docker build -t my-springboot-app .'
    }
}
stage('Push Docker Image') {
    steps {
        withCredentials([usernamePassword(credentialsId: 'dockerhub-creds')]) {
            sh 'docker push my-springboot-app'
        }
    }
}
        // build docker image
        // stage('BuildDockerImage'){
        //     steps{
        //     withDockerRegistry([credentialsId: "dockerlogin", url:""]){
        //         script{
        //            app =  docker.build("tech365app")
                 
        //         }
        //     }
        //     }
        // }

        // push docker image
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

        // stage('kubernetes deployment'){
        //     steps{
        //         withKubeConfig([credentialsId: 'kubelogin']){
        //             sh('kubectl delete all -n devsecops')
        //             sh ('kubectl apply -f deployment.yaml --namespace=devsecops')
        //         }
        //     }
            
        // }
    }
}
