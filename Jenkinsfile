pipeline {
    agent any
    tools {
        maven 'maven_3_6_0'
    }
    stages {
        stage ('Compile Stage') {

            steps {                
                    bat 'mvn clean compile'                
            }
        }

        stage ('Testing Stage') {

            steps {                
                    bat 'mvn test'                
            }
        }
         stage('results') {
             steps {
                junit '**/target/surefire-reports/TEST-*.xml'
             }
        }       
       
    }    
}
