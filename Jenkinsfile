pipeline {
    agent any
    triggers{
        pollSCM('*/1 * * * *')
    }
    stages {
        stage('build-api-test-image') {
            steps {
                buildDockerImage()
            }
        }
    }
}

def buildDockerImage(){
    //tagging with margarita121/api-tests-final:latest since api-tests already exists
    echo "Building of api-tests-final is starting.."
    sh "docker build -t margarita121/api-tests-final:latest ."

    echo "Pushing image to docker registry.."
    sh "docker push margarita121/api-tests-final:latest"
}