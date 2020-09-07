pipeline {
    agent any
    environment {
        ENV_NAME = "lol"
    }    
    parameters {
        string(name: 'multimarca', defaultValue: 'Hello', description: 'How should I greet the world?')  
        string(name: 'tiene', defaultValue: '', description: 'tienes?')  
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
                echo "${params.multimarca} World! ${ENV_NAME}"
                script {
                    if ( tiene != '') {
                        ENV_NAME = """domain${params.multimarca}_${params.zona}"""
                    } else {
                        ENV_NAME = """domain${ENV_NAME}"""
                    }
                    switch(zona){
                        case 'one':
                            ENV_NAME = """one"""
                            break
                        case 'two':
                            ENV_NAME = """two"""
                            break
                        default:
                            ENV_NAME = """damn"""
                            break
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
        stage('LOL2'){
            steps {
                echo "${params.multimarca} World! ${ENV_NAME}"
            }
        }
    }
    post {
        always {
            echo 'genial'
        }
    }
}
