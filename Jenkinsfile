def gv

pipeline {
    tools{
        maven 'Maven'
    }
    agent any
    stages {
        stage("init") {
            steps {
                script {
                    gv = load "script.groovy"
                }
            }
        }
        stage("build jar") {
             steps {
                script{
                    sh 'mvn package'
                }
             }
        }
        stage("build image") {
             steps {
                script{
                    withCredentials([usernamePassword(credentialsId: 'docker-hub-repo', passwordVariable:'PASS', usernameVariable:'USER' )])
                    sh 'docker build -t light3739/java_maven:1.0 .'
                    sh "echo $PASS | docker login -u $USER --password-stdin"
                    sh 'docker push light3739/java_maven:1.0'
                }
             }
        }


    }
}