pipeline {

    def nodeHome = tool name: 'Node6', type: 'jenkins.plugins.nodejs.tools.NodeJSInstallation'
    env.PATH = "${nodeHome}/bin:${env.PATH}"

    agent {
        docker {
            image 'node:7.4'
        }
    }
    stages {
        stage('npm-build') {
            steps {
                echo "Branch is ${env.BRANCH_NAME}..."
                withNPM(npmrcConfig: 'npm-artifactory') {
                    sh 'npm install'
                }
            }
        }
    }
}