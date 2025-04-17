pipeline {
    agent any

    tools {
        sonarScanner 'sonar-scanner'
    }

    environment {
        JAVA_HOME = "/usr/lib/jvm/java-11-openjdk-amd64"
        PATH = "${JAVA_HOME}/bin:${env.PATH}"
    }

    stages {
        stage('Checkout from Git') {
            steps {
                git url: 'https://github.com/liwencee/Netflix-Like-App.git', branch: 'main'
            }
        }

        stage('Check Java') {
            steps {
                sh '''
                    echo "JAVA_HOME is: $JAVA_HOME"
                    which java
                    java -version
                '''
            }
        }

        stage('Sonarqube Analysis') {
            steps {
                withSonarQubeEnv('sonar-server') {
                    sh '''
                        sonar-scanner \
                          -Dsonar.projectName=Netflix \
                          -Dsonar.projectKey=Netflix
                    '''
                }
            }
        }

        stage("quality gate") {
            steps {
                timeout(time: 1, unit: 'MINUTES') {
                    waitForQualityGate abortPipeline: true
                }
            }
        }
    }
}
