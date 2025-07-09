pipeline {
    agent an

        stage('Install Dependencies') {
            steps {
                sh 'pip install -r requirements.txt'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t jenkins-demo-app .'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh 'docker stop jenkins-demo || true'
                sh 'docker rm jenkins-demo || true'
                sh 'docker run -d --name jenkins-demo -p 5000:5000 jenkins-demo-app'
            }
        }
    }
}
