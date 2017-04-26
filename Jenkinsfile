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
                withEnv(["PATH+NODE=${tool name: 'Node6'}/bin"]) {
                    echo "Branch is ${env.BRANCH_NAME}..."
                    withNPM(npmrcConfig: 'npm-artifactory') {
                        sh 'npm install'
                    }
                }
            }
        }
    }
}