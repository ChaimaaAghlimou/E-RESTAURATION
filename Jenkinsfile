pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {	               
	            git branch: 'main', url: 'https://github.com/ChaimaaAghlimou/E-RESTAURATION.git'
            }
        }
        stage('Contrôle qualité') {
            steps {
                sh '''
                # Add sonarqube_project and sonarqube_token to the Jenkins configuration pipeline
                sonar-scanner \
                  -Dsonar.projectKey=$sonarqube_project \
                  -Dsonar.sources=. \
                  -Dsonar.host.url=http://sonarqube:9000 \
                  -Dsonar.token=$sonarqube_token
                '''
            }
        }
       
    }
       
}
