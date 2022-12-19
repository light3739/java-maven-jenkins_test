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
                    echo 'hello'
                }
             }
        }


    }
}