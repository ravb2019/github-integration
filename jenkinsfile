node('master') {
    stage('Fetch Source code') {
        git 'https://github.com/ravb2019/github-integration.git'
    }

    printMessage('Running pipeline')

    stage('Testing') {
        sh 'python test_functions.py'
    }

    stage('Deployment') {
        if (env.BRANCH_NAME == 'master') {
            printMessage('Deploying to Master')
        } else {
            printMessage('No deployment configured for this branch')
        }
    }
}

def printMessage(message) {
    echo "${message}"
}


