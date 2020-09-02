pipeline {
    agent any
    parameters {
        string(name: 'multimarca', defaultValue: 'Hello', description: 'How should I greet the world?')
        choice(name: 'zona', choices: ['one', 'two', 'three'], description: 'No way?')
    }
    stages {
        stage('Test') {
            steps {
                echo 'hola'
                echo "Running ${env.BUILD_ID} on ${env.JENKINS_URL}"
                echo "${params.multimarca} World! ${params.zona}"
                @VALOR='echo ${params.multimarca}'
                echo "${VALOR}"
                echo "${params.multimarca} World! ${params.zona}"
                sh '''
                    echo "Multiline shell steps works too"
                    echo lol
                '''
                sh 'date'
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
