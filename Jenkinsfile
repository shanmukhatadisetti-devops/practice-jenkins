pipeline{
    agent {
        label 'agent-1'
    }
    environment {
        course = "Jenkins"
    }
    options {
         timeout(time: 10, unit: 'SECONDS')
         disableConcurrentBuilds()
    } 
    stages {
        stage('build') {
            steps {
                script {
                    sh """
                        echo "Build"
                        env
                        sleep 10
                    """
                }


            }
        }
        stage('test') {
            steps{
                echo "test"
            }
        }
        stage('Deploy'){
            steps{
                echo "Deploy"
            }
        }


    }
    post {
        always {
            echo "I will always say Hello"
            deleteDir()
        }
        success {
            echo "Hello success"
        }
        failure {
            echo "Hello failure"
        }
    }
}