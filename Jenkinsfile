tools {
    jdk 'jdk11'
    sonarQube 'sonar-scanner'
}
stage('Sonarqube Analysis') {
    steps {
        withSonarQubeEnv('sonar-server') {
            sh '''$SCANNER_HOME/bin/sonar-scanner -Dsonar.projectName=Netflix \
            -Dsonar.projectKey=Netflix'''
        }
    }
    
}
