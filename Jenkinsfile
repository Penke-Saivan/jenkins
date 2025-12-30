pipeline {

    // ------------pre-build-----------------

    // agent configured
    agent {
    node {
        label 'AGENT-1'
        
    }

}

// parameters

parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }

    
// environment variables
environment { 
        COURSE = 'Jenkin'
    }
//  after the timeout abort the pipeline    
    options {
        timeout(time: 10, unit: 'MINUTES') 
        disableConcurrentBuilds()
    }

// ------------------- build stage -----------------------  
    stages {
        stage('Building') {
            steps {
                script{
                    sh """
                        echo "Building----------A-Build"
                        echo "COurse we learn is : $COURSE"
                        sleep 10
                        env
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

    // --------------------------post build--------------------
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
            echo "may be timeeout  -aborted--------------------------------"
        }
    }
}