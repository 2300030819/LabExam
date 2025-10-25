pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'master', url: 'https://github.com/2300032663/CICDEXAM.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                bat 'npm install'
            }
        }

        stage('Build Frontend') {
            steps {
                bat 'npm run build'
            }
        }

        stage('Deploy') {
    steps {
        echo 'Deploying build files to local folder...'
        // Option 1: using double backslashes
        bat 'xcopy /E /I /Y dist\\* C:\\Users\\mah\\hospital-deploy\\'
        // OR Option 2: using forward slashes
        // bat 'xcopy /E /I /Y dist/* C:/Users/mah/hospital-deploy/'
    }
}
    }


    post {
        success {
            echo '✅ Frontend deployed successfully!'
        }
        failure {
            echo '❌ Deployment failed! Check logs.'
        }
    }
}
