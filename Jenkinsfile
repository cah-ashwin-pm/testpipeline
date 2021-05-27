#!/usr/bin/env groovy

pipeline {

    agent any
    // parameters {}
    stages {

        stage('Setup') {
            
            steps {

                script {

                    echo "Setup Started..."
                    sh "chmod +x ./pipeline-scripts/*"
                    env.DOCKER_BASE = "docker.io"
                    env.DOCKER_ACCOUNT_NAME = "ashwinprakash99"
                    env.CLIENT_IMAGE = "testclient"
                    env.CLIENT_TAG = "0.0.1-" + currentBuild.number
                    env.SERVER_IMAGE = "testserver"
                    env.SERVER_TAG = "0.0.1-" + currentBuild.number
                    env.ARTIFACTORY_CRED_ID = "docker-registry-credentials"
                    env.BRANCH_PATTERN = "main|develop|test-dev|^TS-.*|PR-\\d+"
                    env.REGEXP = "REGEXP"
                    env.DOCKER_ACCOUNT_NAME = "ashwinprakash99"
                    echo "Setup Finished..."

                }

            }

        }
        // stage('Client Application Test') {

        //     when {

        //         anyOf {
        //             branch pattern: BRANCH_PATTERN, comparator: REGEXP
        //         }

        //     }
        //     steps {

        //         script {

        //             echo "Client Application Test Started..."
        //             sh "./pipeline-scripts/client_test.sh"
        //             echo "Client Application Test Finished..."
                
        //         }

        //     }

        // }
        // stage('Server Application Test') {
            
        //     when {

        //         anyOf {
        //             branch pattern: BRANCH_PATTERN, comparator: REGEXP
        //         }

        //     }
        //     steps {
                
        //         script {

        //             echo "Server Application Test Started..."
        //             sh "./pipeline-scripts/server_test.sh"
        //             echo "Server Application Test Finished..."

        //         }

        //     }

        // }
        // stage('Docker Client Application Build And Push') {

        //     when {

        //         anyOf {
        //             branch pattern: BRANCH_PATTERN, comparator: REGEXP
        //         }

        //     }
        //     environment {
        //         ARTIFACTORY_CRED = credentials("$ARTIFACTORY_CRED_ID")
        //     }
        //     steps {

        //         script {

        //             echo "Docker Client Application Build And Push Started..."
        //             sh "./pipeline-scripts/client_docker_build_push.sh"
        //             echo "Docker Client Application Build Finished..."

        //         }
        //     }

        // }
        // stage('Docker Server Application Build And Push') {

        //     when {

        //         anyOf {
        //             branch pattern: BRANCH_PATTERN, comparator: REGEXP
        //         }

        //     }
        //     environment {
        //         ARTIFACTORY_CRED = credentials("$ARTIFACTORY_CRED_ID")
        //     }
        //     steps {
                
        //         script {

        //             echo "Docker Server Application Build And Push Started..."
        //             sh "./pipeline-scripts/server_docker_build_push.sh"
        //             echo "Docker Server Application Build Finished..."

        //         }

        //     }

        // }

        stage('TestTestTest') {
            when {
                anyOf {
                    branch pattern: BRANCH_PATTERN, comparator: REGEXP
                }
            }
            steps {
                script {
                    env.TEST = sh returnStdout: true, script: 'mvn help:evaluate -Dexpression="project.version" | grep -Ev "(^\\[.*|Down.*)"'
                }
            }
        }

        // stage('Deploy') {

        //     steps {
        //         sh "echo 'Deploy Stage'"
        //     }

        // }
        // stage('Verify') {

        //     steps {
        //         sh "echo 'Verify Stage'"
        //     }

        // }

    }

}
