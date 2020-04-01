pipeline {
    agent none
    stages {
	
	stage('build') {
        steps {
                echo builing....
                sh build.sh
                }
        }
	
    stage('unit') {
        steps {
            echo unit testing....
            sh unit.sh
        }

    stage('deploy') {
        steps {
            echo deploying....
            sh deploy.sh
        }
    stage('qa') {
        steps {
            echo qa......
            sh quality.sh
        }
        
    }
}
