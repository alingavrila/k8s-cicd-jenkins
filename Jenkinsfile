@Library('demo-maven') _
pipeline {
    agent any
    environment {
        DOCKER_CRED = 'dockerhub'
    }

    stages {
        stage("Checkout code") {
            steps {
                welcome.checkoutCodeNPM()
            }
        }
        stage("Build image") {
            steps {
                script {
                    welcome.buildImageNpm()
                }
            }
        }
        stage("Push image") {
            steps {
                script {
                    welcome.pushImageMvn()
                }
            }
        }
    }


    // stages {
    //     stage("Checkout code") {
    //         steps {
    //             checkout scm
    //         }
    //     }
    //     stage("Build image") {
    //         steps {
    //             script {
    //                 myapp = docker.build("alingavrila/nodejs-test:${env.BUILD_ID}")
    //             }
    //         }
    //     }
    //     stage("Push image") {
    //         steps {
    //             script {
    //                 docker.withRegistry('https://registry.hub.docker.com', 'dockerhub') {
    //                         myapp.push("latest")
    //                         myapp.push("${env.BUILD_ID}")
    //                 }
    //             }
    //         }
    //     }        
    // }
}
