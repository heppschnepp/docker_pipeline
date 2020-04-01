pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                echo 'builing....'
                // Permission to execute
                sh "chmod +x -R ${env.WORKSPACE}/../${env.JOB_NAME}@script"
                // Call SH
                sh "${env.WORKSPACE}/../${env.JOB_NAME}@script/build.sh"
            }
        }
        
        stage('unit') {
            steps {
                echo 'unit testing....'
                sh "${env.WORKSPACE}/../${env.JOB_NAME}@script/unit.sh"
            }
        }

        stage('deploy') {
            steps {
                echo 'deploying....'
                sh "${env.WORKSPACE}/../${env.JOB_NAME}@script/deploy.sh"
            }
        }

        stage('qa') {
            steps {
                echo 'qa......'
                sh "${env.WORKSPACE}/../${env.JOB_NAME}@script/quality.sh"
            }
        }    
    }
}