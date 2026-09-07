pipeline {
    agent any

    triggers {
        pollSCM('* * * * *')
    }

    stages {
        stage('Build') {
            steps {
                echo 'Task: Compile the source code and package it into a deployable artefact.'
                echo 'Tool: Maven'
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo 'Task: Run unit tests to verify individual components, then run integration tests to verify the components work together.'
                echo 'Tool: JUnit for unit tests and Selenium for integration tests'
            }
        }

        stage('Code Analysis') {
            steps {
                echo 'Task: Analyse the source code against industry coding standards and report maintainability issues.'
                echo 'Tool: SonarQube'
            }
        }

        stage('Security Scan') {
            steps {
                echo 'Task: Scan the code and its dependencies for known vulnerabilities and report the findings.'
                echo 'Tool: OWASP Dependency-Check'
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo 'Task: Deploy the packaged application to the staging server for pre-production verification.'
                echo 'Tool: AWS CLI deploying to an AWS EC2 instance'
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo 'Task: Run integration tests against the staging environment to confirm the application behaves correctly in a production-like setting.'
                echo 'Tool: Postman with Newman'
            }
        }

        stage('Deploy to Production') {
            steps {
                echo 'Task: Promote the verified build and deploy the application to the production server.'
                echo 'Tool: AWS CLI deploying to an AWS EC2 instance'
            }
        }
    }
}
