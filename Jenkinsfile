stage('npm-build') {
    agent {
        docker {
            image 'node:7.4'
        }
    }
    steps {
        echo "Branch is ${env.BRANCH_NAME}..."
        withNPM(npmrcConfig: 'npm-artifactory') {
            sh 'npm install'
        }
    }
}