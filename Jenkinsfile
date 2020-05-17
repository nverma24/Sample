pipeline {
    agent {
        docker { image 'master' }
    }
    stages {
        stage('Test') {
            steps {
                script {
                    
                    withMaven(jdk: 'java', maven: 'Maven') {
                           
                            sh """
                                cd $WORKSPACE
                                mvn clean install
                            """
                    }
                }
        }
    }
}
