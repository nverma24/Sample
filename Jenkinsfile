pipeline {
    
    stage('Initialize'){
        def dockerHome = tool 'myDoc'
        env.PATH = "${dockerHome}/bin:${env.PATH}"
    }
    agent {
        docker { image 'myDoc' }
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
}
