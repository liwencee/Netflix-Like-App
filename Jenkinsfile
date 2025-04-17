stage('SonarQube Analysis') {
    steps {
        withSonarQubeEnv('sonar-server') {  // Ensure 'sonar-server' matches the config in Jenkins
            script {
                // Run the SonarQube analysis using the configured SonarQube Scanner
                sh '''${tool "sonar-scanner"}/bin/sonar-scanner \
                -Dsonar.projectName=Netflix \
                -Dsonar.projectKey=Netflix \
                -Dsonar.host.url=http://your.sonarqube.server.url'''
            }
        }
    }
}
