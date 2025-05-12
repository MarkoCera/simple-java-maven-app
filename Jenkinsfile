pipeline {
    agent any
    
    environment {
        DEPLOY_USER = 'cera'
        DEPLOY_HOST = '172.25.100.152'
        DEPLOY_PATH = '/tmp/pipeline-scm'
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
