pipeline {
    agent {
        label 'centos'
    }

    stages {
        stage('Hello') {
            steps {
                echo 'Run moleculd test for vector-role'
            }
        }
        stage('Clear work dir befor') {
            steps {
                deleteDir()
            }
        }
        stage('Run git') {
            steps {
                dir('vector-role') {
                git branch: 'main', credentialsId: 'a8e0a375-e5a2-47f6-8e78-0a35f29f8bd1', url: 'https://github.com/kirill-karagodin/vector-role.git'
                }
            }
        }
        stage('Install molecule') {
            steps {
                sh 'pip3 install "molecule==3.4.0"'
                sh 'pip3 install molecule-docker'
            }
        }
        stage('Check version') {
            steps {
                sh 'molecule --version'
            }
        }
        stage('Check dir') {
            steps {
                dir('vector-role') {
                sh 'ls -la'
                }
            }
        }
        stage('Molecule test') {
            steps {
                dir('vector-role') {
                sh 'molecule test -s ubuntu_latest'
                }
            }
        }
    }
}
