pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Criando venv..'
                sh 'python3 -m venv devops'
                echo 'Entrando na venv e instalando bibliotecas..'
                sh '''
                    # Usar bash explicitamente
                    bash -c "source devops/bin/activate && pip install flask flask-cors"
                '''
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying....'
                sh '''
                    bash -c "source devops/bin/activate && python3 main.py --host=0.0.0.0 &"
                '''
            }
        }
    }
}
