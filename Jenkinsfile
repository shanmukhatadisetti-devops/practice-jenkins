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
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
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
                echo "${params.PERSON}"
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