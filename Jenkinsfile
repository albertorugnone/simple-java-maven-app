pipeline {
    agent {
        docker {
            image 'maven:3-alpine' 
            args '-v /root/.m2:/root/.m2' 
        }
    }
    stages {
        stage('Effettive Pom') { 
            steps {
                sh 'mvn org.apache.maven.plugins:maven-help-plugin:3.1.0:effective-pom' 
            }
        }
        stage('Build') { 
            steps {
                sh 'mvn -B -DskipTests clean package' 
            }
        }
    }
}