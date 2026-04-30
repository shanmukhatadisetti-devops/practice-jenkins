pipeline{
    agent {
        label 'agent-1'
    } 
    stages {
        stage('build') {
            steps {
                echo 'build'

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