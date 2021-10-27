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
        
        stage('Coleta Info') {
            steps {
                echo 'Informacoes da Distro utilizada'
                sh '''
                  echo "================================" >> assessment.txt
                  echo "================================" >> assessment.txt
                  cat /etc/*-release >> assessment.txt
                  echo "================================" >> assessment.txt
                  echo "================================" >> assessment.txt
                  uname -a >> assessment.txt
                  echo "================================" >> assessment.txt
                  echo "================================" >> assessment.txt
                  cat /etc/passwd | cut -d: -f1 >> assessment.txt
                  echo "================================" >> assessment.txt
                  echo "================================" >> assessment.txt
                  dpkg -l >> assessment.txt
                  
                  '''
            }
            
        }
    }
    
    post {
        always { echo "Eu sempre vou ser executado!"}
        success { echo "Somente serei executado quando finalizar com sucesso!"}
        failure { echo "Somentei serei executado quando finalizar com erro!"}
    }
    
}
