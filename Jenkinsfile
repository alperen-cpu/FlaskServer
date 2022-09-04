pipeline {
    agent any
    stages {        
        stage('Docker build and deploy') {
            steps {
                sh '''
                pwd
                unzip FlaskServer.zip
                docker build --pull -t flaskapp:$BUILD_NUMBER FlaskServer/.
                docker run -d -p 3000:3000 flaskapp:$BUILD_NUMBER
                rm -rf *
                '''
            }
        }      
    }
}