def gv

pipeline {
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
                script {
                    echo "building jar"
                    env.versions = input message:"Select version", ok:"Done",parameters: [choice(name:"VERSIONS",choices:['1','2','prod']),description:'']
                    }
                }
            }
        stage("build image") {
            steps {
                script {
                    echo "$versions"
                    //gv.buildImage()
                }
            }
        }
        stage("deploy") {
            steps {
                script {
                    echo "deploying"
                    //gv.deployApp()
                }
            }
        }
    }   
