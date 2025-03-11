pipeline (
    agent any
    stages [
        stage('Clone repository') {
            steps (
                checkout ([$class: 'GitSCM', branches: [[name: '*/main']], 
                userRemoteConfigs: [[url: 'https://github.com/pes2ug22cs579/PES2UG22CS579_Jenkins.git']]])
            )
        }
        stage("Build") {
            steps {
                build 'PES2UG22CS579-1'
                sh 'g++ main.cpp -o output'
            }
        }
        stage('Test') {
            steps {
                sh './output'
            }
        }
        stage("Deploy") {
            steps {
                echo "deploy"
            }
        }
    ]
    post {
        failure {
            error "Pipeline failed"
        }
    }
)
