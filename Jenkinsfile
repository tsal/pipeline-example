pipeline {
    agent {
        docker {
            image 'node:7.4'
        }
    }
    environment {
        def nodeHome = tool name: 'Node6'
    }
    stages {
        stage('npm-build') {
            steps {
                echo "Branch is ${env.BRANCH_NAME}..."
                withNPM(npmrcConfig: 'npm-artifactory') {
                    sh 'whoami'
                    sh 'npm install'
                }
            }
        }
    }
}