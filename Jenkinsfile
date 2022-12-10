pipeline {
    agent any
    triggers {
        cron('H/2 * * * *')
    }   
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
        stage ('Starting ART job') {
            steps {
                build job: 'base-c'
            }
        }
       
    }    
    post {         
         always {
             junit '**/target/surefire-reports/TEST-*.xml'
        }              
    }
}
