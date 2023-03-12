pipeline {
    agent { label 'NODE_2' }
    triggers { 
        pollSCM('* 23 * * 1-5')
    }
    stages {
        stage('vcs') {
            steps {
                git url: 'https://github.com/khajadevopsmarch23/StudentCoursesRestAPI',
                    branch: 'sprint_1_release'
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