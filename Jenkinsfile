pipeline{
    agent {
        label 'agent-1'
    }
    environment {
        course = "Jenkins"
    } 
    stages {
        stage('build') {
            steps {
                script {
                    sh """
                        echo "Build"
                        env
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