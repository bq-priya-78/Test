pipeline {
    agent any
    environment
    {
        name = 'priya'
    }
    parameters{
       string(name: 'person', defaultValue: 'priya', description: 'who are you' )
       booleanParam(name: 'isMale', defaultValue: true, description: "")
       choice(name: 'city', choices:['mumbai','jaipur','agra'], description:"")
    }
    stages {
        stage('RUN as a Command') {
            steps {
                sh '''
                ls
                pwd 
                ls
                pwd
                '''
            }
        }
        stage('Test') {
             environment
              {
                username = 'priyagoyal'
              }
            
            steps {
                sh 'echo "${BUILD_ID}"'
                sh 'echo "${name}"'
                sh 'echo "${person}"'
            }
        }
        stage('Continue') {
            steps {
                echo 'Deployment'
                sh 'echo "${username}"'
                sh 'echo "${isMale}"'
            }
        }
        stage('Deployforprod') {
            steps {
                echo 'Deployment for production'
                echo 'Hii'
            }
        }
    }
    post{
        always{
                echo "i am running always"
            }
            
        }
   }
