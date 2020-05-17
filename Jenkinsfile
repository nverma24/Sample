pipeline {
    
    
    agent {
        docker { image 'myDoc' }
    }
    stages {
        stage('Initialize'){
        def dockerHome = tool 'myDoc'
        env.PATH = "${dockerHome}/bin:${env.PATH}"
    }
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
