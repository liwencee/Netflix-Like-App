stage("Sonarqube Analysis") {
    environment {
        JAVA_HOME = "/usr/lib/jvm/java-11-openjdk-amd64"
        PATH = "${JAVA_HOME}/bin:${env.PATH}"
    }
    steps {
        withSonarQubeEnv('sonar-server') {
            sh '''
              echo "JAVA_HOME is set to: $JAVA_HOME"
              java -version
              sonar-scanner \
                -Dsonar.projectKey=Netflix \
                -Dsonar.projectName=Netflix
            '''
        }
    }
}
