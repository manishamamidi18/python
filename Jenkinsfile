
pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'master',
                    url: 'https://github.com/manishamamidi18/python.git'
            }
        }

        stage('Compile') {
            steps {
                bat 'python -m py_compile app.py apptest.py'
            }
        }

        stage('Test') {
            steps {
                bat 'python -m unittest apptest -v'
            }
        }

        stage('Run Application') {
            steps {
                bat 'python app.py'
            }
        }

       stage('Package') {
    steps {
        bat 'powershell -Command "Compress-Archive -Path app.py, apptest.py, requirements.txt -DestinationPath python.zip -Force"'
    }
}
    }
}
