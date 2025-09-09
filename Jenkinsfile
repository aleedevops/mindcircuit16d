pipeline {
    agent any

    stages {
        
        stage('clone scm') {
            steps {
                echo 'this is source code git repo'
                git branch: 'main', url: 'https://github.com/aleedevops/mindcircuit16d.git'
            }
        }
         stage('build') {
            steps {
                echo 'this stage build code using maven'
                sh 'mvn clean install'
            }
        }
            stage('deploy') {
                steps {
                    echo 'this stage deploy  code .war to tomcat webserver'
                    deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: 'StrongPassword123', path: '', url: 'http://18.234.44.87:8080/')], contextPath: 'alee', war: '**/*.war'
                    
                }
            }
    }
    
}
