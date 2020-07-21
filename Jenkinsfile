pipeline {
    agent any

    stages {
        stage ('Compile Stage') {

            steps {
                //withMaven(maven : 'maven_3_6_3') {
                    //sh 'mvn clean compile'
                withMaven(tool name: 'maven_3_6_3', type: 'maven_3_6_3)' 
                sh "/bin/mvn package"
                }
            }
        }

        stage ('Testing Stage') {

            steps {
                withMaven(maven : 'maven_3_6_3') {
                    sh 'mvn test'
                }
            }
        }


        stage ('Deployment Stage') {
            steps {
                withMaven(maven : 'maven_3_6_3') {
                    sh 'mvn deploy'
                }
            }
        }
    }
