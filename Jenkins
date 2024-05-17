pipeline {
    agent any
    
    environment {
        NODE_VERSION = '14' // Versão do Node.js a ser instalada
    }
    
    stages {
        stage('Checkout') {
            steps {
                // Este estágio é usado para verificar o código-fonte do repositório Git
                // Substitua a URL do repositório conforme necessário
                checkout scm
            }
        }
        
        stage('Install Node.js') {
            steps {
                // Este estágio é usado para instalar o Node.js
                script {
                    sh "curl -sL https://deb.nodesource.com/setup_${NODE_VERSION}.x | bash -"
                    sh "apt-get install -y nodejs"
                }
            }
        }
        
        stage('Install Vite') {
            steps {
                // Este estágio é usado para instalar o Vite
                sh 'npm install -g create-vite-app'
            }
        }
        
        stage('Create React App with Vite') {
            steps {
                // Este estágio é usado para criar o aplicativo React com Vite
                sh 'create-vite-app my-react-app --template react-ts'
            }
        }
        
        stage('Start Dev Server') {
            steps {
                // Este estágio é usado para iniciar o servidor de desenvolvimento do Vite
                dir('my-react-app') {
                    sh 'npm run dev'
                }
            }
        }
        
        stage('Build') {
            steps {
                // Este estágio é usado para compilar o código-fonte, se necessário
                // Neste exemplo, não realizaremos nenhuma compilação, apenas um echo
                echo 'Building...'
            }
        }
        
        stage('Deploy') {
            steps {
                // Este estágio é usado para implantar a aplicação em um ambiente de produção
                // Neste exemplo, apenas um echo é usado
                echo 'Deploying...'
            }
        }
    }
    
    post {
        always {
            // Este bloco de pós-processamento é executado após a conclusão de qualquer estágio
            // Neste exemplo, apenas um echo é usado
            echo 'Pipeline finished'
        }
    }
}
