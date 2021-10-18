pipeline {
   agent any

   stages {
      stage('Verify Branch') {
         steps {
            echo "$GIT_BRANCH"
         }
      }
      stage('Docker Build') {
         steps {
            echo 'docker not possible'
            /*pwsh(script: 'docker images -a')
            pwsh(script: """
               cd azure-vote/
               docker images -a
               docker build -t jenkins-pipeline .
               docker images -a
               cd ..
            """)*/
         }
      }
      stage('Start test app') {
         steps {
            echo 'starting app'
            /*pwsh(script: """
               docker-compose up -d
               ./scripts/test_container.ps1
            """)*/
         }
         post {
            success {
               echo "App started successfully :)"
            }
            failure {
               echo "App failed to start :("
            }
         }
      }
      stage('Run Tests') {
         steps {
            pwsh(script: """
               pytest C:/Users/I551939/OneDrive - SAP SE/Documents/learnings/Jenkins/azure-app/azure-voting-app-redis/tests/test_sample.py
            """)
         }
      }
      stage('Stop test app') {
         steps {
            echo 'stopping'
            /*pwsh(script: """
               docker-compose down
            """)*/
         }
      }
   }
}
