pipeline {
    agent any

    stages {
        stage ('Compile Stage') {

            steps {
                withMaven(maven : 'localMAVEN') {
                    sh 'mvn clean compile'
                }
            }
        }

        stage ('Testing Stage') {

            steps {
                withMaven(maven : 'localMAVEN') {
                    sh 'mvn test'
                }
            }
        }
        
        stage ('Package Stage'){
            steps{
                withMaven(maven: 'localMAVEN'){
                    sh 'mvn package'
                }
            }
        }
        
        stage ('Verify Stage'){
            steps{
                withMaven(maven: 'localMAVEN'){
                    sh 'mvn verify'
                }
            }
        }
        

        stage ('Deployment Stage') {
            steps {
                withMaven(maven : 'localMAVEN') {
                    sh 'mvn install'
                }
            }
        }
    }
}
