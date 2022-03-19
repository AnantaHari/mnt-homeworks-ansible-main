pipeline {
    agent {
        label 'linux'
    }
    stages {
        stage('checkout role'){
            steps{
                dir('mnt-homeworks-ansible'){
                    git branch: 'main', credentialsId: '71f28e48-74fb-4a6a-a514-c82ecf7b80fd', url: 'git@github.com:AnantaHari/mnt-homeworks-ansible-main.git'
                }
            }
        }
        stage('Install molecule') {
            steps{
                dir('mnt-homeworks-ansible'){
                    sh 'cd mnt-homeworks-ansible && pip3 install -r test-requirements.txt'
                }
                sh "echo =============="
            }
        }
        stage('Run Molecule'){
            steps{
                dir('mnt-homeworks-ansible'){
                    sh 'cd mnt-homeworks-ansible && molecule test'
                }
            }
        }
    }
}