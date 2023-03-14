pipeline {
    agent { label 'mynode' }
    triggers { 
        pollSCM('* * * * *')
    }
    stages {
        stage('vcs') {
            steps {
                git url: 'https://github.com/nkishore555/StudentCoursesRestAPI.git',
                    branch: 'develop'
            }
        }
        stage('build') {
            steps {
                sh 'docker image build -t kishorekrrish/student:6.0 .'
            }
        }
        stage('scan and push') {
            steps {
                sh 'echo docker scan kishorekrrish/student:6.0'
                sh 'docker image push kishorekrrish/student:6.0'
            }
        }
    }

}
