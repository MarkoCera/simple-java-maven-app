

pipeline {
    agent any
    tools {
      maven "MAVEN3.9.9"
    }
    stages {
        stage('Build') { 
            steps {
                sh 'mvn -B -DskipTests clean package' 
            }
        }
    }
}

