pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {	               
	            git branch: 'main', url: 'https://github.com/ChaimaaAghlimou/E-RESTAURATION.git'
            }
        }
        // stage clone permetter de cloner le projet 
        stage('Contrôle qualité') {
            steps {
                sh '''
                # Add sonarqube_project and sonarqube_token to the Jenkins configuration pipeline
                sonar-scanner \
                  -Dsonar.projectKey=chaimaa_E-RESTAURATION  \
                  -Dsonar.sources=. \
                  -Dsonar.host.url=http://192.168.1.24:9000 \
                  -Dsonar.token=sqp_6dbf1fc4c541a66ed39686f6da68a13d49fd35d8
                '''
            }
        }
       
    }
       
}
