pipeline {
    agent any
    options {
        buildDiscarder logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '', daysToKeepStr: '10', numToKeepStr: '4')
        disableConcurrentBuilds()
        timeout(30)
        retry(3)

    }
    parameters {
        booleanParam defaultValue: false, name: 'Run unit tests'
        string defaultValue: 'master', name: 'BRANCH'
        choice choices: ['dev', 'qa', 'prod', 'UAT'], name: 'Environment'
    }
    triggers {
        cron 'H * * * *'
    }


    stages {
        stage('First Step') {
            steps {
                echo 'Hello World'
                sh "sleep 10"
            }
        }
        stage('Second Step') {
            steps {
                echo 'Hello World'
            }
        }        
    }
}
