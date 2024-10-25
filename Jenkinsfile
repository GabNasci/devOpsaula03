pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Criando venv..'
                sh 'python3 -m venv devops'
                echo 'Entrando na venv..'
                sh 'source devops/bin/activate'
                echo 'Instalando bibliotecas..'
                sh 'pip install flask'
                sh 'pip install flask-cors'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying....'
                sh 'python3 main.py --host=0.0.0.0 &'
            }
        }
    }
}
