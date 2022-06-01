pipeline{
    agent{label 'nodejs'}
    stages{
        stage('source code'){
            steps{
                git url:'https://github.com/Rajanikanthraju/python-sample-vscode-flask.git',
                    branch:'sprint_develop'
            }
        }
        stage ('install dependencies'){
            steps{
                sh 'pip install'
                sh 'pip setuptools wheel'
            }
        }
    }
    }