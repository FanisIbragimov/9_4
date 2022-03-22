pipeline {
    agent {
        label 'linux'
    }
    stages {
        stage('checkout role'){
            steps{
                dir('9_4') {
                    git branch: 'main', credentialsId: '04dc2180-5b74-4c89-abd4-ef1098b5be10', url: 'https://github.com/FanisIbragimov/9_4.git'
                }
            }
        }
        stage('Install molecule') {
            steps{
                dir('9_4'){
                    sh 'pip3 install -r test-requirements.txt'
                }
                sh "echo =============="
            }
        }
        stage('Run Molecule'){
            steps{
                dir('9_4'){
                    sh 'molecule test'
                }
            }
        }
    }
}
