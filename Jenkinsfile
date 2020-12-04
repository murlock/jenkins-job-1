pipeline {
    agent any;
    options {
        copyArtifactPermission('*,/murlock,/murlock/*,/murlock/jenkins-job-2,/my-github/jenkins-job-2/master,/my-github/*')
    }
    stages {
        stage('Build') {
            steps {
                sh '''
                echo "magic" > magic
                '''
            }
        }
    }
    post {
        success {
            archiveArtifacts artifacts: 'magic', fingerprint: true
        }
    }
}
