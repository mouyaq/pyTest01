pipeline {
    agent any

    stages {
        // stage('Initialize') {
        //     def dockerHome = tool 'myDocker'
        //     env.PATH = "${dockerHome}/bin:${env.PATH}"
        // }
        stage('Test1') {
            agent {
                docker {
                    image 'node:7-alpine'
                    // args '--name docker-node' // list any args
                }
            }
            steps {
                echo 'TEST1-1'
                sh 'node --version'
            }
        }
        stage('Test2') {
            steps {
                echo 'TEST2-1'
                echo 'TEST2-2'
            }
        }
        stage('Test3') {
            steps {
                echo 'TEST3-1'
                echo 'TEST3-2'
                echo 'TEST3-3'
                sh 'python --version'
            }
        }
    }
    post {
        always {
            echo 'This will always run'
        }
        success {
            echo 'This will run only if successful'
        }
        failure {
            echo 'This will run only if failed'
        }
        unstable {
            echo 'This will run only if the run was marked as unstable'
        }
        changed {
            echo 'This will run only if the state of the Pipeline has changed'
            echo 'For example, if the Pipeline was previously failing but is now successful'
        }
    }
}