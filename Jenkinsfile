pipeline {
    agent { label 'mynode' }
    trigger { 
        pollSCM('* * * * *')
        stages {
        stage('vcs') {
            steps {
                git url : 'https://github.com/nkishore555/StudentCoursesRestAPI.git'
                    branch: 'master'
            }
        }
        stage('build') {
            steps {
                sh 'docker build -t kishorekrrish/student:5.0 .'
                sh 'docker push kishorekrrish/student:5.0'
            }
        }
    }
    }
}
