pipeline {
    agent any
    
    parameters {
        string(
            name: 'IMAGE_URL',
            defaultValue: "/docker.io/username/repository:tag",
            description: 'Enter the image URL'
        )
        choice(
            name: 'ENVIRONMENT',
            choices: ['dev', 'staging', 'production'],
            description: 'Select the environment'
        ),
        booleanParam(
            name: 'ENABLE_FEATURE',
            defaultValue: true,
            description: 'Enable or disable the feature'
        )
    }

    environment {
        APP_URL_DEV = "https://dev.eventmetro.com"
        APP_URL_STAGE = "https://stage.eventmetro.com"
        APP_URL_PROD = "https://eventmetro.com"
    }

    stages {
        stage('Select Environment') {
            steps {
                script {
                    switch(params.ENVIRONMENT) {
                        case 'dev':
                            env.APP_URL = env.APP_URL_DEV
                        break

                        case 'staging':
                            env.APP_URL = env.APP_URL_STAGE

                        case 'production':
                            env.APP_URL = env.APP_URL_PROD

                        default:
                            error('Invalid environment selected')

                    }
                }

                echo "Selected Environment: ${params.ENVIRONMENT}"
                echo "Application URL: ${env.APP_URL}"
            }
        }
        stage('test') {
            steps {
                echo "Testing application: ${env.APP_URL}"
                echo "Docker Image URL: ${params.IMAGE_URL}"

                script {
                    if(params.ENABLE_FEATURE){
                        echo "Feature is enabled"
                    } else {
                        echo "Feature is disabled"
                    }
                }

                echo 'Application test completed successfully!'
            }
        }

        stage('test') {
            steps {
                echo "Building for ${params.ENVIRONMENT}"
                echo "Using image: ${params.IMAGE_URL}"

                echo 'Project build completed successfully!'
            }
        }
    }
}
