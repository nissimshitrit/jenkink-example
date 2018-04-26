pipeline {
    agent any
    tools {
        maven 'maven_3_0_5'
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
        steps {
                bat 'cd'
                //bat 'mkdir reports'
                bat 'xcopy /S ..\\..\\hpdevops-discovery-demoapp-master\\reports\\* reports'
                bat 'sleep 2'
        }
       
    }
    post {
        always {
            step([$class: 'XUnitBuilder',
                thresholds: [[$class: 'FailedThreshold', unstableThreshold: '1']],
                tools: [[$class: 'JUnitType', pattern: 'reports/resultsSet1/TEST*.xml']]])
        }
    }
}
