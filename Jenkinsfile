pipeline {
    agent any    
    stages {
        stage ('Compile Stage') {

            steps {                
                    bat 'mvn clean compile'                
            }
        }

        stage ('Testing Stage') {

            steps {                
                    bat 'mvn -Dmaven.test.failure.ignore test'                
            }
        }
         stage('results') {
             steps {
                junit '**/target/surefire-reports/TEST-*.xml'
             }
        }       
    }    
}
