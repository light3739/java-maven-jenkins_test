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
        stage("AWS Demo") {
                    steps {
                   withCredentials([[
                       $class: 'AmazonWebServicesCredentialsBinding',
                       credentialsId: "	jenkins2 ",
                       accessKeyVariable: 'AWS_ACCESS_KEY_ID',
                       secretKeyVariable: 'AWS_SECRET_ACCESS_KEY'
                   ]]) {
                       sh 'aws s3 ls'
                   }
                    }
                }


    }
}