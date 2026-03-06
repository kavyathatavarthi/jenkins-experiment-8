pipeline {
    agent any
    parameters {
        // Task 2: Define a string parameter
        string(name: 'PROJECT_NAME', defaultValue: 'Experiment8_Project', description: 'Enter Project Name')
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
    }
}