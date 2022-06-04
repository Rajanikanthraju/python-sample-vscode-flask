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
        stage('Test Results'){
            steps{
                sh 'pip install pytest'
                sh '/home/jenkins/.local/bin/pytest --doctest-modules --junitxml=junit/test-results.xml --cov=. --cov-report=xml'
                }
        }
        
        stage('SonarQube analysis') {
            steps{
                withSonarQubeEnv('SONAR_LATEST') { 
                   sh '/home/jenkins/sonar-scanner-4.7.0.2747-linux/bin/sonar-scanner \
                                                -Dsonar.projectKey=pythontest \
                                                -Dsonar.sources=. \
                                                -Dsonar.host.url=http://50.18.238.53:9000 \
                                                -Dsonar.login=8c59c6166034be6db2ba7145988fd68dc8d18c15'
                                                  }
                 }
            }
        
       }
    }