pipeline{
    agent{
        label 'ansible'
    }
    stages{
        stage('checkout git'){
            steps{
                git branch: 'main', credentialsId: '04dc2180-5b74-4c89-abd4-ef1098b5be10', url: 'https://github.com/FanisIbragimov/9_4.git'
            }
        }
        stage('install dependencies'){
            steps{
                sh 'pip3 install -r test-requirements.txt'
            }
        }
        stage('run molecule'){
            steps{
                sh 'molecule test'
            }
        }
    }
}
