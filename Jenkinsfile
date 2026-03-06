pipeline {
    agent any
    parameters {
        // Task 2: Define a string parameter
        string(name: 'PROJECT_NAME', defaultValue: 'Experiment8_Project', description: 'Enter Project Name')
        // Task 2: Define a numeric parameter (string type is used for input in Jenkins)
        string(name: 'BUILD_ID', defaultValue: '1001', description: 'Enter Numeric Build ID for Version 2')
        // Task 2: Define two parameters
        string(name: 'APP_NAME', defaultValue: 'MyApplication', description: 'Enter App Name')
        string(name: 'VERSION', defaultValue: 'v1.0', description: 'Enter Version')
        // Task 2: Ensure all parameters are defined
        string(name: 'PROJECT_NAME', defaultValue: 'Exp8', description: '')
        string(name: 'BUILD_ID', defaultValue: '8', description: '')
        string(name: 'APP_NAME', defaultValue: 'PipelineLab', description: '')
        string(name: 'VERSION', defaultValue: '2.0', description: '')
    }
    stages {
        stage('Version 1') {
            steps {
                // Task 1: Checkout source code
                checkout scm
                // Task 3: Display the value in console
                echo "Task 3: The PROJECT_NAME value is: ${params.PROJECT_NAME}"
            }
        }
        stage('Version 2') {
            steps {
                // Task 1: Checkout updated repository
                checkout scm
                
                // Task 3: Save value inside buildinfo.txt and display it
                // Using 'bat' for Windows systems
                bat "echo ${params.BUILD_ID} > buildinfo.txt"
                echo "Reading contents of buildinfo.txt:"
                bat "type buildinfo.txt"
            }
        }
        stage('Version 3') {
            steps {
                // Task 1: Checkout latest version
                checkout scm
                // Task 3: Display combined message
                echo "Task 3: Deployment of ${params.APP_NAME} at version ${params.VERSION} is ready."
            }
        }
        stage('Version 4') {
            steps {
                // Task 1: Checkout latest commit
                checkout scm
                
                // Task 2 (Display all):
                echo "Displaying Parameters: Project=${params.PROJECT_NAME}, ID=${params.BUILD_ID}, App=${params.APP_NAME}, Ver=${params.VERSION}"
                
                // Task 3 (Store in parameters.txt):
                bat """
                echo Project: ${params.PROJECT_NAME} > parameters.txt
                echo BuildID: ${params.BUILD_ID} >> parameters.txt
                echo AppName: ${params.APP_NAME} >> parameters.txt
                echo Version: ${params.VERSION} >> parameters.txt
                """
                echo "Contents of parameters.txt:"
                bat "type parameters.txt"
            }
        }
    }
}