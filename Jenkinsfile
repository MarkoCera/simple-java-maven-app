pipeline {
    agent any
    
    environment {
        DEPLOY_USER = 'cera'
        DEPLOY_HOST = '192.168.1.11'
        DEPLOY_PATH = '/tmp/'
    }
    
    tools {
        maven "MAVEN3.9.9"
    }
    
    stages {
        stage('Build') {
            steps {
                sh 'mvn -B -DskipTests clean package'
            }
        }
        stage('Deploy') {
            steps {
                sh '''
                scp target/*.jar $DEPLOY_USER@$DEPLOY_HOST:$DEPLOY_PATH
                '''
            }
        }
    }
    
}
