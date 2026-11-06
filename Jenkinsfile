pipeline {
    agent any
    
    environment {
        IMAGE_URL = "docker.io/username/repository:tag"
    }

    parameters {
        string(
            name: 'IMAGE_URL',
            defaultValue: "${IMAGE_URL}",
            description: 'Enter the image URL'
        )
    }

    stages {
        stage('test') {
            steps {
                echo "${IMAGE_URL} is the image url"
                echo 'Project test successfully hosted on github...'
                echo "${params.IMAGE_URL} is the image url default value is ${params.defaultValue} and description is ${params.description}"
            }
        }
        stage('build') {
            steps {
                echo 'Project build successfully hosted on github...'
            }
        }
    }
}
