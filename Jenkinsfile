pipeline {
    agent any

    stages {
        stage('Sonar Analysis') {
            steps {
                echo 'CODE QUALITY CHECK'
                sh 'cd webapp'
                sh 'sudo docker run --rm -e SONAR_HOST_URL="http://20.173.96.114:9000"     
                -v "$(pwd):/usr/src"     sonarsource/sonar-scanner-cli     
                -Dsonar.projectKey=jen3    
                 -Dsonar.login=sqp_ed85765f3a20c5b67a8a1059616c4bed374c4b0f' 
                echo 'CODE QUALITY COMPLETED'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}

