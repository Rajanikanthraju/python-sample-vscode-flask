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
                sh 'pip install setuptools wheel'
                 }
        }
        stage('Install requirements'){
            steps{
              sh  'pip install -r requirements.txt'
            }
        }
        stage('Test results'){
            steps{
                sh 'pip install pytest pytest-cov'
                sh 'pytest --doctest-modules --junitxml=junit/test-results.xml --cov=. --cov-report=xml'
            }
        }
    }
    }