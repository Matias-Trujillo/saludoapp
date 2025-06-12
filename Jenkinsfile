pipeline {
    agent any

    tools {
        maven 'Maven 3.9.10'   // Debe coincidir con el nombre configurado en Jenkins
        jdk 'JDK 21'           // Igual, debe ser exacto
    }

    stages {
        stage('Clonar') {
            steps {
                git 'https://github.com/Matias-Trujillo/saludoapp.git'
            }
        }

        stage('Compilar') {
            steps {
                sh 'mvn clean compile'
            }
        }

        stage('Probar') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Empaquetar') {
            steps {
                sh 'mvn package'
            }
        }
    }

    post {
        success {
            echo "✅ El build fue exitoso"
        }
        failure {
            echo "❌ El build falló"
        }
    }
}
