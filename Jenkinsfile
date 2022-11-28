pipeline {
    agent {
        docker {
            image 'alesyademyanchuk/sspr'
        }
    }
    stages {
        stage('Cloning Git') {
          steps {
              git([url: 'https://github.com/Alesya-23/sspr2.git', branch: 'master'])
          }
        }
        stage('Test') {
            steps {
                sh 'java -version'
                sh " ./gradlew build --args='--sspr2.check-run=true'"
                sh "./gradlew test"
            }
        }
    }
}