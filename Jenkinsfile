pipeline {
    agent any

    stages {
        stage('verify branch') {
            steps {
                echo "$GIT_BRANCH"
            }
        }

        stage('Docker Build') {
            steps {
                echo 'no docker in docker'
                /*
                sh 'docker images -a'
                sh """
                    cd azure-vote/
                    docker images -a
                    docker build -t jenkins-pipeline .
                    docker images -a
                    cd ..
                """
                */
            }
        }
    }
}
