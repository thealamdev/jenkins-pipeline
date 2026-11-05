pipeline {
    agent any
    
    environment {
        IMAGE_URL = "docker.io/username/repository:tag"
    }

    stages {
        stage('test') {
            steps {
                echo "${IMAGE_URL} is the image url"
            }
        }
        stage('build') {
            steps {
                echo 'Project build successfully hosted on github...'
            }
        }
    }
}
