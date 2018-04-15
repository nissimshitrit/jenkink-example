pipeline {
    agent any
    tools {
        maven 'apache-maven-3.0.5' 
    }
    stages {
        stage ('Compile Stage') {

            steps {                
               sh 'mvn clean compile'                
            }
        }

        stage ('Testing Stage') {

            steps {               
                sh 'mvn test'               
            }
        }


        stage ('Deployment Stage') {
            steps {                
                    sh 'mvn deploy'                
            }
        }
    }
}
