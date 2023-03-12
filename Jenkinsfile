pipeline {
    agent { label 'NODE_2' }
    triggers { 
        pollSCM('* * * * *')
    }
    stages {
        stage('vcs') {
            steps {
                git url: 'https://github.com/khajadevopsmarch23/StudentCoursesRestAPI',
                    branch: 'develop'
            }
        }
        stage('build') {
            steps {
                sh 'docker image build -t vishnu2508/spc:latest .'
            }
        }
        stage('scan and push') {
            steps {
                sh 'echo docker scan vishnu2508/spc:latest'
                sh 'docker image push vishnu2508/spc:latest'
            }
        }
    }

}