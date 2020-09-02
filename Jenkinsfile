pipeline {
    agent any
    environment {
        ENV_NAME = "lol"
    }    
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
                echo "=============================== TEST"
                echo "=============================== TEST"
                script {
                    if ( multimarca == 'Hello') {
                        echo "SI"
                        ENV_NAME = '->Development'${params.multimarca}'_'${params.zona}' 
                    } else {
                        ENV_NAME = 'Production'
                    }
                }
                echo "${params.multimarca} World! ${ENV_NAME}"
                echo "=============================== TEST"
                echo "=============================== TEST"
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
