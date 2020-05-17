pipeline {
    
    
    agent {
        docker { image 'myDoc' }
    }
    stages {
        
        stage('Test') {
            steps {
                script {
                    def dockerHome = tool 'myDoc'
        env.PATH = "${dockerHome}/bin:${env.PATH}"
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
