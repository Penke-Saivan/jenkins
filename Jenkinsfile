pipeline {
    agent {
    node {
        label 'AGENT-1'
        
    }



}
environment { 
        COURSE = 'Jenkin'
    }
    stages {
        stage('Building') {
            steps {
                script{
                    sh """
                        echo "Building----------A-Build"
                        echo "COurse we learn is : $COURSE"
                       """ 
                }
            }
        }
        stage('Test') {
            steps {
            script{
                    sh """
                        echo "Building----------A-Test"
                       """ 
                }
            }
        }
        stage('Deploy') {
            steps {
                script{
                    sh """
                        echo "Building----------A-Deployment"
                       """ 
                }
            }
        }
    }
        post { 
        always { 
            echo 'I will always say Hello again!'
            cleanWs()
        }
        success{
            echo "Success---------------"
        }
        failure{
            echo "failure---------------"
        }
        aborted{
            echo "someone -aborted--------------------------------"
        }
    }
}