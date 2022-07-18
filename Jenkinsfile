// Declarative //
pipeline {
  agent any
  environment {
        NAME = 'Kushagra'
    }
  triggers {
        pollSCM('* * * * *')
    }
    stages {
         stage('Build')
          {
            steps {
                echo "Running ${env.BUILD_ID} on ${env.JENKINS_URL}"
                    }
            }
        stage('Test') 
        {
            steps {
              echo "Testing..${NAME}"
            }
        }
        stage('Deploy')
         {
            steps {
                  bat "ls -al"
            }
        }
    }
        post {
            always {
            junit '**/target/*.xml'
        }
        success {
            echo 'I will say Hello only if job is success'
        }
        failure {
             mail to: kushagra2307@gmail.com, subject: 'The Pipeline failed :('
        }
        
    }
}
