pipeline {
    agent any 
    
    environment {
        NOME = "Mario"
        SOBRENOME = "Santana"
        //SECRET = credentials('TEST')
    }
    
    stages {
        stage('Create file assessment.txt') {
            steps {
                echo 'create file'
                sh '''
                  touch assessment.txt
                  date >> assessment.txt
                  '''
            }
            
        }
        
        stage('Build') {
            steps {
                echo 'Informacoes da Distro utilizada'
                sh '''
                  cat /etc/*-release
                  '''
            }
            
        }
        stage('Test') {
            steps {
                echo 'Testando...'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
                //sh 'echo $SECRET'
            }
        }
        stage('Smoke Test') {
            steps {
                echo 'Smoke Test...'
                //sh 'echo $SECRET'
            }
        }
    }
    
    post {
        always { echo "Eu sempre vou ser executado!"}
        success { echo "Somente serei executado quando finalizar com sucesso!"}
        failure { echo "Somentei serei executado quando finalizar com erro!"}
    }
    
}
