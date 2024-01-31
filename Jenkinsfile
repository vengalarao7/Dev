pipeline {
    agent any
        // tools {
        //         maven 'Maven'
        // }

        environment {
                PROJECT_ID = 'terraform-gcp-410710'
                CLUSTER_NAME = 'cluster-2'
                LOCATION = 'europe-west3'
                CREDENTIALS_ID = 'terraform'
        }

    stages {
            // stage('Scm Checkout') {
            //         steps {
            //                 checkout scm
            //         }
            // }

            // stage('Build') {
            //         steps {
            //                 sh 'mvn clean package'
            //         }
            // }

            // stage('Test') {
            //         steps {
            //                 echo "Testing..."
            //                 sh 'mvn test'
            //         }
            // }

            // stage('Build Docker Image') {
            //         steps {
            //                 sh 'whoami'
            //                 script {
            //                         myimage = docker.build("vengalarao7/devops:${env.BUILD_ID}")
            //                 }
            //         }
            // }

            // stage("Push Docker Image") {
            //         steps {
            //                 script {
            //                         echo "Push Docker Image"
            //                         withCredentials([string(credentialsId: 'dockerhub', variable: 'dockerhub')]) {
            //                             sh "docker login -u vengalarao7 -p ${dockerhub}"
            //                             sh "docker push vengalarao7/devops:${env.BUILD_ID}"
            //                             sh "docker images"
            //                         }
            //                 }
            //         }
            // }

            stage('Deploy to K8s') {
                    steps{
                            echo "Deployment started ..."
                            // sh 'ls -ltr'
                            // sh 'pwd'
                            //sh "sed -i 's/tagversion/${env.BUILD_ID}/g' serviceLB.yaml"
                                // sh "sed -i 's/tagversion/${env.BUILD_ID}/g' deployment.yaml"
                           // echo "Start deployment of serviceLB.yaml"
                           // step([$class: 'KubernetesEngineBuilder', projectId: env.PROJECT_ID, clusterName: env.CLUSTER_NAME, location: env.LOCATION, manifestPattern: 'serviceLB.yaml', credentialsId: env.CREDENTIALS_ID, verifyDeployments: true])
                                echo "Start deployment of deployment.yaml"
                                step([$class: 'KubernetesEngineBuilder', projectId: env.PROJECT_ID, clusterName: env.CLUSTER_NAME, location: env.LOCATION, manifestPattern: 'deployment.yaml', credentialsId: env.CREDENTIALS_ID, verifyDeployments: true])
                            echo "Deployment Finished ..."
                    }
            }
    }
}
