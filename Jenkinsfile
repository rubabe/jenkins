pipeline {
    agent { label 'linux' }
    stages {
        stage('download from github') {
            steps {
                echo "Starting to download on linux agent"
                git branch: 'main', url: 'https://github.com/rubabe/jenkins.git'
                sh '''
                echo 'downloaded'
                echo 'running multiline shell command in jenkins'
                '''
            }
        }
        stage('building docker image') {
            steps {
                echo "building image"
                sh 'docker build -t Rubabe/jenkins_sample:1.0 .'
                sh 'echo building finished successfully'
                sh 'sleep 30'
                sh '''
                echo 'working on'
                echo 'slave node'
                '''
            }
        }
        stage('pushing docker image to  docker registry') {
            steps {
                echo "pushing image"
                sh 'docker login -u Rubabe -p Elnureko83.'
                sh 'docker push rubabe/jenkins_sample:1.0'
                sh 'echo pushing to docker registry finished successfully'
                sh 'sleep 30'
                sh '''
                echo 'working on'
                echo 'slave node'
                '''
            }
        }
    }
}
