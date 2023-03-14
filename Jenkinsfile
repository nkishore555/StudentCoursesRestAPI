pipeline {
    agent { label 'mynode' }
    trigger { 
        pollSCM('* * * * *')
        stages {
        stage('vcs') {
            steps {
                git url : 'https://github.com/nkishore555/StudentCoursesRestAPI.git'
                    branch: 'develop' 
            }
        }
        stage('build') {
            steps {
                sh 'docker build -t kishorekrrish/student:4.0 .'
                sh 'docker push kishorekrrish/student:5.0'
            }
        }
    }
    }
}
