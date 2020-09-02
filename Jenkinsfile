pipeline {
    agent any
    parameters {
        string(name: 'multimarca', defaultValue: 'Hello', description: 'How should I greet the world?')
        string(choice: 'zona', defaultValue: 'pepito', description: 'No way?')
    }
    stages {
        stage('Test') {
            steps {
                echo 'hola'
                echo "Running ${env.BUILD_ID} on ${env.JENKINS_URL}"
                echo "${params.multimarca} World! ${params.zona}"
                sh (uname -a)
                sh ("uname -a")
                sh (pwd)
                echo "adios"
            }
        }
    }
    post {
        always {
            echo 'genial'
        }
    }
}
