pipeline {
    agent { label 'aws' }
    triggers { 
        pollSCM('* * * * *')
    }
    stages {
        stage('vcs') {
            steps {
                git url: 'https://github.com/nkishore555/StudentCoursesRestAPI.git',
                    branch: 'master'
            }
        }
        stage('build') {
            steps {
                sh 'docker image build -t kishorekrrish/student:7.0 .'
            }
        }
        stage('scan and push') {
            steps {
                sh 'echo docker scan kishorekrrish/student:7.0'
                sh 'docker image push kishorekrrish/student:7.0'
            }
        }
    }

}
