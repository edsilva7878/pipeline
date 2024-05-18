pipeline {
    agent any
    
    stages {
        stage('Build-V1') {
            steps {
                echo 'Construindo...'
                // Aqui você colocaria os comandos para compilar seu código, como 'mvn compile' para projetos Maven ou 'npm install' para projetos Node.js
            }
        }
        stage('Test') {
            steps {
                echo 'Testando...'
                // Aqui você colocaria os comandos para executar seus testes, como 'mvn test' para projetos Maven ou 'npm test' para projetos Node.js
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deployando...'
                // Aqui você colocaria os comandos para implantar sua aplicação, como 'mvn deploy' para projetos Maven ou 'scp' para transferência de arquivos
            }
        }
    }
    
    post {
        success {
            echo 'Sucesso total!'
            // Aqui você pode adicionar ações a serem realizadas se o pipeline for bem-sucedido, como notificações ou geração de relatórios
        }
        failure {
            echo 'Pipeline com falha :('
            // Aqui você pode adicionar ações a serem realizadas se o pipeline falhar, como notificações ou registros de erro
        }
    }
}

