pipeline {
    agent any
    environment {
        get_pass = credentials('my-password')
    }
    stages {
       stage('build') {
           steps{
               sh '''
               echo "this is building stage"
               date
               echo "we are starting our buil script here"
               jenkins/build/my-mvn.sh mvn -B -DskipTest clean package
               jenkins/build/build.sh
               echo "it's pushed from github"
               echo "latest changing"
               '''

           }

       }

        stage('test') {
            steps{
                echo "this is testing stage"
            }

        }

        stage('deploy') {
            steps{
                echo "this is deploy stage"
            }

        }
    }
}
