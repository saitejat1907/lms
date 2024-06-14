pipeline {
    agent any

    stages {
        stage('Sonar Analysis') {
            steps {
                echo 'CODE QUALITY CHECK'
                sh 'cd webapp'
                sh 'sudo docker run --rm     -e SONAR_HOST_URL="http://20.173.96.114:9000"     -v "$(pwd):/usr/src"     sonarsource/sonar-scanner-cli     -Dsonar.projectKey=jen     -Dsonar.login=sqp_7965264ee1a28b59e82223001cbd591f6dd04483'
                // sh 'sudo docker run --rm -e SONAR_HOST_URL="http://20.173.96.114:9000"  -v "$(pwd):/usr/src"     sonarsource/sonar-scanner-cli    -Dsonar.projectKey=jen3     -Dsonar.login=sqp_ed85765f3a20c5b67a8a1059616c4bed374c4b0f' 
                //  sh '''#!/bin/bash
                //     cd webapp
                //     sudo docker run --rm -e SONAR_HOST_URL="http://20.173.96.114:9000" \
                //     -v "$(pwd):/usr/src" sonarsource/sonar-scanner-cli \
                //     -Dsonar.projectKey=jen3 \
                //     -Dsonar.login=sqp_ed85765f3a20c5b67a8a1059616c4bed374c4b0f'''
                echo 'CODE QUALITY COMPLETED'
            }
        }
        stage('Build LMS') {
            steps {
                echo 'Build LMS'
                sh 'cd webapp && npm install && npm run build'
                echo 'Build Complete'

            }
        }
        stage('Realease lms') {
            steps {
                script {
                    def packageJson = readJSON file: 'webapp/package.json'
                    def packageJSONVersion = packageJson.version
                    echo "${packageJSONVersion}"
                    sh "zip webapp/lms-${packageJSONVersion}.zip -r webapp/dist"
                    sh "curl -v -u admin:sai123 --upload-file webapp/lms-${packageJSONVersion}.zip http://20.173.96.114:8081/repository/lms/"

                }
            }
        }
        stage('Deploy lms') {
            steps {
                script {
                    echo 'Preparing LMS Deployment'
                    def packageJson = readJSON file: 'webapp/package.json'
                    def packageJSONVersion = packageJson.version
                    echo "${packageJSONVersion}"
                    sh "curl -u admin:lms12345 -X GET \'http://20.173.96.114:8081/repository/lms/lms-${packageJSONVersion}.zip\' --output lms-'${packageJSONVersion}'.zip"
                    sh 'sudo rm -rf /var/www/html/*'
                    sh "sudo unzip -o lms-'${packageJSONVersion}'.zip"
                    sh "sudo cp -r webapp/dist/* /var/www/html"
                    echo 'Completed LMS Deployment'
                 }
            }
        }
    }
}

