pipeline {
    agent { node { label 'AGENT-1' } }
    options {
        timeout(time: 1, unit: 'HOURS') 
    }
    environment { 
        USER = 'vinodkumar'
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                /* sh 'ls -ltr'
                sh 'pwd' */
                sh '''
                echo "This line is for testing the webhook configuration"
                 ls -ltr
                 pwd
                 echo "These are CMD to test" 
                 printenv
                '''           
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
      post { 
        always { 
            echo 'I will always run whether job is success or not'
        }
        success{
            echo 'I will run only when job is success'
        }
        failure{
            echo 'I will run when failure'
        }
    }
}

