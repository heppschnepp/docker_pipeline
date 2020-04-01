pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                echo 'builing....'
                // Permission to execute
                sh "chmod +x -R ${env.WORKSPACE}/../${env.JOB_NAME}/*.sh"
                // Call SH
                sh "${env.WORKSPACE}/../${env.JOB_NAME}/build.sh"
            }
        }
        
        stage('unit') {
            steps {
                echo 'unit testing....'
                sh "${env.WORKSPACE}/../${env.JOB_NAME}/unit.sh"
            }
        }

        stage('deploy') {
            steps {
                echo 'deploying....'
                sh "${env.WORKSPACE}/../${env.JOB_NAME}/deploy.sh"
            }
        }

        stage('qa') {
            steps {
                echo 'qa......'
                sh "${env.WORKSPACE}/../${env.JOB_NAME}/quality.sh"
            }
        }    
    }
}