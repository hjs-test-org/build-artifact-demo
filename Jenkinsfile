pipeline {
    agent any

    stages {
        stage('Build') {
            stages {
                stage('Compile') {
                    steps {
                        echo 'Compiling...'
                        sleep 10
                    }
                }
                stage('Package') {
                    steps {
                        echo 'Packaging...'
                        sleep 5
                    }
                }
            }
        }

        stage('Registering build artifact') {
            steps {
                echo 'Registering the metadata'
                echo 'Another echo to make the pipeline a bit more complex'
                registerBuildArtifactMetadata(
                    name: "demo-test-deployment",
                    version: "2.0.0",
                    type: "docker",
                    url: "http://aws.artifacts/6a9acc6aa1be5446a2393ab90e7ca9e218bc07fa",
                    digest: "6a9acc6aa1be5446a2393ab90e7ca9e218bc07fa",
                    label: "preprod,test"
                )
                registerBuildArtifactMetadata(
                    name: "demo-QA-deployment",
                    version: "2.0.0",
                    type: "docker",
                    url: "http://aws.artifacts/94805399282f52bc22e0afdad26dda3bcd28258e",
                    digest: "94805399282f52bc22e0afdad26dda3bcd28258e",
                    label: "nort,south"
                )
                registerBuildArtifactMetadata(
                    name: "demo-prod-deployment",
                    version: "2.0.0",
                    type: "docker",
                    url: "http://aws.artifacts.com/52c22f83e883b55cbc23ca7d207c5a93f5d28089",
                    digest: "52c22f83e883b55cbc23ca7d207c5a93f5d28089",
                    label: "ease,west"
                )
            }
        }

        stage('Test') {
            steps {
                echo 'Running Unit Tests...'
                sleep 10
                echo 'Running Integration Tests...'
                sleep 5
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying...'
                sleep 5
            }
        }
    }
}
