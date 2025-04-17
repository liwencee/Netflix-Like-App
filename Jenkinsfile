tools {
    sonarQubeScanner 'sonar-scanner' // Name from Global Tool Config
}

stages {
    stage('Sonarqube Analysis') {
        steps {
            withSonarQubeEnv('sonar-server') { // Must match Configure System
                sh 'sonar-scanner'
            }
        }
    }
}
