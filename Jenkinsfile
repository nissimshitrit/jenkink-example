pipeline {
    agent any
    tools {
        maven 'maven_3_0_5'
    }
    stages {
        stage ('Compile Stage') {

            steps {                
                    bat 'mvn clean'                
            }
        }

        stage ('Testing Stage') {

            steps {                
                    bat 'mvn test'                
            }
        }


        stage ('Deployment Stage') {
            steps {                
                    bat 'mvn deploy'                
            }
        }
    }
}
