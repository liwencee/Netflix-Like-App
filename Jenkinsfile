stage('Sonarqube Analysis') {
    environment {
        JAVA_HOME = "/usr/lib/jvm/java-11-openjdk-amd64"
        PATH = "${JAVA_HOME}/bin:${env.PATH}"
    }
    steps {
        withSonarQubeEnv('sonar-server') {
            sh '''
                echo "Using JAVA_HOME: $JAVA_HOME"
                java -version
                sonar-scanner \
                  -Dsonar.projectName=Netflix \
                  -Dsonar.projectKey=Netflix
            '''
        }
    }
}
