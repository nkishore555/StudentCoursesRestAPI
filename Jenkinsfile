pipeline {
    agent { label 'mynode' }
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
                sh 'sudo docker image build -t kishorekrrish/student:6.0 .'
            }
        }
        stage('scan and push') {
            steps {
                sh 'sudo echo docker scan kishorekrrish/student:6.0'
                sh 'sudo docker image push kishorekrrish/student:6.0'
            }
        }
    }

}
